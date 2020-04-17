syscalls2插件为一些操作系统和体系结构的系统调用入口和出口提供回调。这种“操作系统内省”在逆向工程中是非常宝贵的。没有它，PANDA只提供了一个不透明的指令流的回放。

通过自动生成代码的魔力，syscalls2成为可能。给定一个包含系统调用列表以及数字和原型的文件，Python脚本将对其进行摘要处理，以生成编译后用于执行所有必要的检测的代码。

如果您查看syscalls2插件目录，您将看到许多用于驱动代码自动生成的文件：

    linux_arm_prototypes.txt
    linux_x86_prototypes.txt
    windows_7_x86_prototypes.txt
    ...
这些文件中的每一行都是带有命名参数的系统调用的原型。每行开头的号码是系统系统调用号。例如，在x86上，将该数字加载到EAX寄存器中，将参数推送到堆栈中，然后执行sysenter指令来调用系统调用。

对于Windows原型，其签名在操作系统版本之间不会发生变化（尽管可以添加或删除函数，更改编号），还有一个额外的自动生成层——一个包含原型本身的master all_Windows_prototypes.txt，createWindowsPrototypes.py脚本使用它来对调用重新编号每个操作系统。volatile的系统调用表用于执行重新编号。

Caveats 注意事项
----

目前支持Linux x86和ARM以及多个版本的Windows x86。目前不支持64位版本的Windows，因为我们尚未实现64位Windows系统调用ABI。64位支持的补丁将非常感谢！

Use 
----

如果你只想使用这个插件，只要读一下这个。

假设您想编写一个插件，当在回放时跟踪到某些Win7系统调用时，该插件会执行某些操作（注意，插件只在回放时操作）。

例如，您可能想知道何时创建进程，何时销毁进程，在这些时间点上对关联的Windows数据结构执行一些查询，以确定诸如pid和进程名之类的内容。

Windows 7的相关系统调用是“NtCreateUserProcess”和“NtTerminateProcess”，它们的原型可以在“windows7-x86-prototypes.txt”中找到。

     NTSTATUS NtCreateUserProcess 
       (PHANDLE ProcessHandle, 
        PHANDLE ThreadHandle, 
        ACCESS_MASK ProcessDesiredAccess, 
        ACCESS_MASK ThreadDesiredAccess, 
        POBJECT_ATTRIBUTES ProcessObjectAttributes, 
        POBJECT_ATTRIBUTES ThreadObjectAttributes,
        ULONG ProcessFlags, 
        ULONG ThreadFlags,
        PRTL_USER_PROCESS_PARAMETERS ProcessParameters, 
        PPROCESS_CREATE_INFO CreateInfo, 
        PPROCESS_ATTRIBUTE_LIST AttributeList)

     NTSTATUS NtTerminateProcess
       (HANDLE ProcessHandle, 
        NTSTATUS ExitStatus)

这时，你可能会问“你怎么知道要关注那些系统调用？”一个很好的问题，不幸的是，我们没有很好的答案。syscalls2插件为各种Windows和Linux系统调用提供了合理的接口。但是你需要把系统接口的工作知识带到它上面。这可能意味着要阅读Russinovich的“Windows内部”。对于Linux，您可以阅读一本书（有几本Linux内核书）或查看手册页和/或源代码。

syscalls2插件为这些与进程相关的系统调用的进入和退出提供回调。“entry”的意思是在sysenter执行之前。我们所说的“exit”是指PANDA将在紧接着sysenter之后执行指令（由syscalls2插件维护的调用堆栈决定）。

您编写的回调函数的前两个参数是指向cpu state env和程序计数器的指针。其余的参数都是表示实际系统调用参数的无符号整数。例如，enter到NtTerminateProcess的回调具有以下类型。

    typedef void (*on_NtTerminateProcess_enter_t)
      (CPUState* env,
       target_ulong pc,
       uint32_t ProcessHandle,
       uint32_t ExitStatus);

 如果您将此类型签名与上面NtTerminateProcess的类型签名进行比较，您将很容易观察到通信。使用PPP机制向syscalls2注册回调。也就是说，如果你在你的插件中编写了一个函数my_NtTerminateProcess_enter，使其具有on_NtTerminateProcess_enter_t上的类型，那么你可以在插件的init_plugin函数中添加以下内容来注册它。 

     PPP_REG_CB("syscalls2", on_NtTerminateProcess_enter, my_NtTerminateProcess_enter);

此时，您可能需要研究win7proc插件中的代码类型，该插件在Windows 7上使用syscalls2，还包括一些用于检索对象和遍历Windows句柄表的粗代码。或者，您可能会盯着文件污染插件中的代码，该插件使用syscalls2和Linux和Windows跟踪文件打开和读取操作，并使用该插件将污染标签添加到从文件读取的字节中。这是两个很好的例子，说明了使用syscalls2可以做什么。

注意，syscalls2的结构是这样的：如果一个系统调用在多个操作系统中共享相同的语义，那么您可以用一个回调来拦截它。例如，一旦您编写了上面的on_NtTerminateProcess_enter回调，就不需要额外的工作就可以让它在Windows XP SP3上工作了.您只需要使用-panda syscalls2:profile=Windows_XP SP3_x86而不是Windows_7_x86运行插件。

操作系统配置文件
----

一旦您编写了一个使用syscalls2的插件，就必须在panda命令行上启用它，这样syscalls2就知道在尝试使用回调来检测系统调用时应该采用什么操作系统。如果你的插件被称为我的插件，那么要在Win7 32位重播上运行该插件，命令行应该包含

    -panda 'syscalls2:profile=windows_7_x86'
There are currently five supported OS profiles.

    windows_7_x86
    windows_xpsp2_x86
    windows_xpsp3_x86
    linux_x86
    linux_arm

Autogenerating system call introspection
----

如果您对我们如何自动生成系统调用内省代码的细节感兴趣，这里有一个草图。

注意，为系统调用构建内省代码所需的所有信息都包含在调用原型中，除了一些关于系统调用如何在体系结构和操作系统上工作的领域知识之外。可以运行syscalls2目录中的脚本recreate_all_os_arch.sh重新生成代码。然后，该脚本只需运行脚本syscall_parser.py，并使用参数告诉它为命令行上给定的操作系统和体系结构生成代码。

脚本生成以下文件：

    gen_syscalls_ext_typedefs.h

此文件包含每个系统调用原型的两行，并定义了“enter”和“return”回调的类型。

    gen_syscall_ppp_boilerplate_enter.cpp
    gen_syscall_ppp_boilerplate_return.cpp
    gen_syscall_ppp_register_enter.cpp
    gen_syscall_ppp_register_return.cpp
    gen_syscall_ppp_extern_enter.h
    gen_syscall_ppp_extern_return.h

这六个文件都是使PPP为系统调用工作所必需的代码。

最后，对于每个操作系统，我们将有两个文件，其中包含负责处理每个系统调用的代码。它们包含一个大的C switch statment，每个系统呼叫号码都有一个case。对于每个调用，调用的参数都是可用的，然后在所有注册的回调上运行。

    gen_syscall_switch_enter_linux_x86.cpp
    gen_syscall_switch_return_linux_x86.cpp

Adding Support for a New Operating System
----

Hz: syscall2_cn.md没有说添加新的体系结构.
添加对新操作系统的支持相对简单，只要您有一个格式正确的原型文件。例如，假设要添加newos，这是一个x86操作系统。原型文件将命名为newos_x86_prototypes.txt。然后：

1.将newos添加到syscall_parser.py中的已知_OS变量

2.编辑新文件 recreate_all_os_arch.sh并将newos x86添加到命令行的末尾。

3.在syscalls2.cpp中为它添加另一个枚举，并为它填写每个配置文件函数指针；这些函数实际上告诉syscalls2系统调用ABI是什么（即，如何检索系统调用参数）。

4.在in it_plugin的if语句中添加另一个case，以便它将newos_x86识别为有效的配置文件。

5.将gen_syscall_switch_enter_newos_x86.cpp和gen_syscall_switch_return_newos_x86.cpp文件添加到生成文件。

6.将syscall_enter_newos_x86和syscall_return_newos_x86函数的原型添加到syscalls2.h。

7.重新运行./recreate_all_os_arch.sh以生成switch语句的代码。







