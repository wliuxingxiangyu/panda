Plugin: syscalls2
===========

Summary
-------

“syscalls2”插件提供回调，允许在guest中发生系统调用时发出通知，并且只要guest操作系统是“syscalls2”支持的这些操作系统之一，就可以为每个系统调用提供参数。

这是通过基于初始原型文件自动生成一堆代码来实现的。有关详细信息，请查看“syscalls2/syscall_parser.py”和其中一个原型文件，如“syscalls2/prototypes/linux_x86_prototypes.txt”。

For adding support for a new OS or updating the existing ones, see the `syscalls2` [maintenance documentation][prototypes/MAINTENANCE.md].

Arguments
---------

* `profile`字符串，默认为“linux_x86”。要使用的guest操作系统配置文件。这决定了系统调用（如“sysenter”指令）的实际解释方式。可用选项有：linux_x86, linux_arm, windows_xpsp2_x86, windows_xpsp3_x86, and windows_7_x86.
* `load-info`：布尔值，默认为“false”。允许加载所选操作系统配置文件的系统调用信息。这允许对系统调用事件进行更通用的处理，而不必实现单个hooks。


Dependencies
------------

None.

APIs and Callbacks
------------------

### Callbacks
The `syscalls2` plugin defines one callback for each system call in each operating system (far too many to list here). To see the prototypes for each one, you can look at the file `gen_syscalls_ext_typedefs.h`.

Each callback is named `on_${SYSCALLNAME}_enter` for calls and `on_${SYSCALLNAME}_return` for returns. The parameters are the CPU state pointer, program counter, and then the arguments to the system call.

In addition to the OS-specific system calls, there are four callbacks defined that apply to all OSes:

1.Name: **on_unknown_sys_enter**

Signature:

```C
typedef void (*on_unknown_sys_enter_t)(CPUState *env, target_ulong pc, target_ulong callno)
```

Description: Called when an unknown system call (i.e., one that does not have a callback already defined for it) is invoked in the guest. The system call number will be available in the `callno` parameter.

2.Name: **on_unknown_sys_return**

Signature:

```C
typedef void (*on_unknown_sys_return_t)(CPUState *env, target_ulong pc, target_ulong callno)
```

Description: Called when an unknown system call (i.e., one that does not have a callback already defined for it) returns in the guest. The system call number will be available in the `callno` parameter.

3.Name: **on_all_sys_enter**

Signature:

```C
typedef void (*on_all_sys_enter_t)(CPUState *env, target_ulong pc, target_ulong callno)
```

Description: Called for every system call invoked in the guest. The call number is available in the `callno` parameter. This callback does minimal processing on the side of `syscalls2` plugin.

4.Name: **on_all_sys_return**

Signature:

```C
typedef void (*on_all_sys_return_t)(CPUState *env, target_ulong pc, target_ulong callno)
```

Description: Called whenever any system call returns in the guest. The call number is available in the `callno` parameter. This callback does minimal processing on the side of `syscalls2` plugin.

5.Name: **on_all_sys_enter2**

Signature:

```C
typedef void (*on_all_sys_enter2_t)(CPUState *cpu, target_ulong pc, const syscall_info_t *call, const syscall_ctx_t *rp)
typedef void (*on_all_sys_enter_t) (CPUState *env, target_ulong pc, target_ulong callno).................................in function Name: **on_all_sys_enter**.
```

Description: 为guest中调用的每个系统调用调用调用。call参数用于提供有关系统调用的信息。rp参数用于提供有关系统调用上下文的信息（asid、参数值等）。这意味着syscalls2插件需要一些额外的处理。需要为syscalls2启用load info标志才能使用此回调变量。
Called for every system call invoked in the guest. The `call` parameter is used to provide information about the system call. The `rp` parameter is used to provide information about the context of the system call (asid, argument values etc). This means that some additional processing is required on the side of the `syscalls2` plugin. You need to have the `load-info` flag enabled for `syscalls2` to use this variant of the callback.

6.Name: **on_all_sys_return2**

Signature:

```C
typedef void (*on_all_sys_return2_t)(CPUState *cpu, target_ulong pc, const syscall_info_t *call, const syscall_ctx_t *rp)
typedef void (*on_all_sys_return_t) (CPUState *env, target_ulong pc, target_ulong callno).................................in function Name:**on_all_sys_return**
```

Description: 每当任何系统调用在guest中返回时调用。call参数用于提供有关系统调用的信息。rp参数用于提供有关系统调用上下文的信息（asid、参数值等）。这意味着syscalls2插件需要一些额外的处理。需要为syscalls2启用load info标志才能使用此回调变量。
Called whenever any system call returns in the guest. The `call` parameter is used to provide information about the system call. The `rp` parameter is used to provide information about the context of the system call (asid, argument values etc). This means that some additional processing is required on the side of the `syscalls2` plugin. You need to have the `load-info` flag enabled for `syscalls2` to use this variant of the callback.


### API calls
Finally the plugin provides two API calls:

1.Name: **get_syscall_info**

Signature:

```C
const syscall_info_t *get_syscall_info(uint32_t callno)
```

Description: Returns a pointer to a `syscall_info_t` struct containing information about the specified system call. Available only when the `load-info` flag of the plugin has been turned on.

2.Name: **get_syscall_meta**

Signature:

```C
const syscall_meta_t *get_syscall_meta(void)
```

Description: Returns a pointer to a `syscall_meta_t` struct containing meta-information about the system calls of the guest operating system. Available only when the `load-info` flag of the plugin has been turned on.



Example
-------

一般来说，一个插件使用syscalls2，另一个插件为特定的系统调用集 注册回调。例如，可以编写一个名为filereadmon的插件，该插件使用以下内容拦截对Windows上NtReadFile的调用：
In general one uses `syscalls2` with another plugin that registers callbacks for specific set of system calls. For example, one could write a plugin called `filereadmon` that intercepts calls to `NtReadFile` on Windows using something like:

```C
#include "../syscalls2/gen_syscalls_ext_typedefs.h"
#include "../syscalls2/syscalls_common.h"
#include "panda/plugin_plugin.h"

void my_NtReadFile_enter(
        CPUState* env,
        target_ulong pc,
        uint32_t FileHandle,
        uint32_t Event,
        uint32_t UserApcRoutine,
        uint32_t UserApcContext,
        uint32_t IoStatusBlock,
        uint32_t Buffer,
        uint32_t BufferLength,
        uint32_t ByteOffset,
        uint32_t Key) {
   printf("NtReadFile(FileHandle=%x, Event=%x, UserApcRoutine=%x, "
                     "UserApcContext=%x, IoStatusBlock=%x, Buffer=%x, "
                     "BufferLength=%x, ByteOffset=%x, Key=%x)\n",
        FileHandle, Event, UserApcRoutine, UserApcContext,
        IoStatusBlock, Buffer, BufferLength, ByteOffset, Key);
}

// ...

bool init_plugin(void *self) {
    PPP_REG_CB("syscalls2", on_NtReadFile_enter, my_NtReadFile_enter);
    return true;
}

// ...

```

And then invoke it as:

```sh
$PANDA_PATH/x86_64-softmmu/qemu-system-x86_64 -replay foo \
    -os windows-32-7 -panda syscalls2:profile=windows_7_x86 -panda filereadmon
```

If you'd like more examples, you can have a look at `win7proc` and `file_taint`, which both use `syscalls2` extensively.

hzExp
---

```
wanghuozhu@dlserver:~/ws/other/panda/x86_64-softmmu$  ./qemu-system-x86_64 -replay hi  -os linux-64-ubuntu:4.15.0-65-generic  -panda syscalls2: linux-64-ubuntu:4.15.0-65-generic /yiyuan/data/home/wanghuozhu/ws/snapshot/iie_snapshot/snapshot_4M_1d_12h_29m_8s.img

PANDA[core]:os_familyno=2 bits=64 os_details=ubuntu:4.15.0-65-generic
PANDA[syscalls2]:adding argument .
PANDA[core]:initializing syscalls2
PANDA[syscalls2]:no support for 64-bit linux  # hz-
FAIL: Unable to load plugin `/yiyuan/data/home/wanghuozhu/ws/other/panda/x86_64-softmmu/panda/plugins/panda_syscalls2.so'
Aborted (core dumped)
wanghuozhu@dlserver:~/ws/other/panda/x86_64-softmmu$
```

```
     ‘snapshot=SNAPSHOT’
          SNAPSHOT is "on" or "off" and controls snapshot mode for the given drive (see ‘-snapshot’).

    In case you don’t care about data integrity over host failures, use ‘cache=unsafe’.  This option tells QEMU that it never needs to write any data to the disk but can instead keep things in cache.
     If anything goes wrong, like your host losing power, the disk storage getting disconnected accidentally, etc.  your image will most probably be rendered unusable.  When using the ‘-snapshot’ option, unsafe caching is always used.

‘-snapshot’
     Write to temporary files instead of disk image files.  In this case, the raw disk image you use is not written back.  You can however force the write back by pressing <C-a s> (*note disk_images::).



     2.7.2 Snapshot mode :
If you use the option ‘-snapshot’, all disk images are considered as read only.  When sectors in written, they are written in a temporary file created in ‘/tmp’.  You can however force the write back to the raw disk images by using the ‘commit’ monitor command (or <C-a s> in the serial console).




When using the (unrelated) ‘-snapshot’ option (*note disk_images_snapshot_mode::), you can always make VM snapshots, but they are deleted as soon as you exit QEMU.

VM snapshots currently have the following known limitations:
   • They cannot cope with removable devices if they are removed or inserted after a snapshot is done.
   • A few device drivers still have incomplete snapshot support so their state is not saved or restored properly (in particular USB).



‘-s, --snapshot’
     Use FILENAME as an external snapshot, create a temporary file with backing_file=FILENAME, redirect the write to the temporary one
‘-l, --load-snapshot=SNAPSHOT_PARAM’
     Load an internal snapshot inside FILENAME and export it as an read-only device, SNAPSHOT_PARAM format is ’snapshot.id=[ID],snapshot.name=[NAME]’ or ’[ID_OR_NAME]’


     What you should _never_ do:
   • use non-ASCII filenames ;
   • use "-snapshot" together with ":rw:" ;
   • expect it to work when loadvm’ing ;
   • write to the FAT directory on the host system while accessing it with the guest system.

     * -snapshot:                             sec_invocation.     (line  713)


```