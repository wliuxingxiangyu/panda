```
install panda in docker   https://github.com/panda-re/panda
S1:
sudo apt-get install docker.io

S2: take a long time.
sudo docker pull pandare/panda

S3:
docker run --rm pandare/panda -- /bin/panda-system-i386 --help 

wanghuozhu@dlserver:~$ sudo docker run --rm pandare/panda -- /bin/panda-system-i386 --help
[sudo] password for wanghuozhu: 
docker: Error response from daemon: OCI runtime create failed: container_linux.go:345: starting container process caused "exec: \"--\": executable file not found in $PATH": unknown.
wanghuozhu@dlserver:~$ 

```

```
wanghuozhu@dlserver:~/ws/other/panda/panda/scripts$ ./install_ubuntu.sh 
Reading package lists... Done
W: The repository 'http://ppa.launchpad.net/freenx-team/ppa/ubuntu xenial Release' does not have a Release file.
N: Data from such a repository can't be authenticated and is therefore potentially dangerous to use.
N: See apt-secure(8) manpage for repository creation and user configuration details.
W: The repository 'http://ppa.launchpad.net/freenx-team/trusty/ubuntu xenial Release' does not have a Release file.
N: Data from such a repository can't be authenticated and is therefore potentially dangerous to use.
N: See apt-secure(8) manpage for repository creation and user configuration details.

E: Failed to fetch http://ppa.launchpad.net/freenx-team/ppa/ubuntu/dists/xenial/main/binary-amd64/Packages  404  Not Found [IP: 2001:67c:1560:8008::15 80]
E: Failed to fetch http://ppa.launchpad.net/freenx-team/trusty/ubuntu/dists/xenial/main/binary-amd64/Packages  404  Not Found [IP: 2001:67c:1560:8008::15 80]
E: Some index files failed to download. They have been ignored, or old ones used instead.
wanghuozhu@dlserver:~/ws/other/panda/panda/scripts$ 

ans:
ppa-remove
```

```
wanghuozhu@dlserver:~/ws/other/panda$ ./build.sh 
Building with default gcc/g++.
Using protobuf 2.6.1.
Found LLVM on /usr/lib/llvm-3.3 -- LLVM SUPPORT IS ENABLED

ERROR: DTC (libfdt) version >= 1.4.2 not present. Your options:
         (1) Preferred: Install the DTC (libfdt) devel package
         (2) Fetch the DTC submodule, using:
             git submodule update --init dtc

wanghuozhu@dlserver:~/ws/other/panda$ 
```

```
  CC      hw/usb/hcd-xhci.o
  CC      hw/usb/hcd-musb.o
  CC      hw/usb/dev-hub.o
  CC      hw/usb/dev-hid.o
  CC      hw/usb/dev-wacom.o
  CC      hw/usb/dev-storage.o
  CC      hw/usb/dev-uas.o
  CC      hw/usb/dev-audio.o
  CC      hw/usb/dev-serial.o
  CC      hw/usb/dev-network.o
  CC      hw/usb/dev-bluetooth.o
  CC      hw/usb/dev-smartcard-reader.o
  CC      hw/usb/ccid-card-passthru.o
  CC      hw/usb/ccid-card-emulated.o
  CC      hw/usb/dev-mtp.o
  CC      hw/usb/quirks.o
  CC      hw/usb/redirect.o
  CC      hw/usb/host-libusb.o
  CC      hw/usb/host-legacy.o
  CC      hw/usb/xen-usb.o
  CC      hw/virtio/virtio-rng.o
  CC      hw/virtio/virtio-pci.o
  CC      hw/virtio/virtio-bus.o
  CC      hw/virtio/virtio-mmio.o
  CC      hw/virtio/vhost-stub.o
  CC      hw/watchdog/watchdog.o
  CC      hw/watchdog/wdt_i6300esb.o
  CC      hw/watchdog/wdt_ib700.o
  CC      hw/watchdog/wdt_aspeed.o
  CC      hw/xen/xen_backend.o
  CC      hw/xen/xen_devconfig.o
  CC      hw/xen/xen_pvdev.o
  CC      migration/migration.o
  CC      migration/socket.o
  CC      migration/exec.o
  CC      migration/fd.o
  CC      migration/tls.o
  CC      migration/colo-comm.o
  CC      migration/colo.o
  CC      migration/colo-failover.o
  CC      migration/vmstate.o
  CC      migration/qemu-file.o
  CC      migration/qemu-file-channel.o
  CC      migration/postcopy-ram.o
  CC      migration/qjson.o
  CC      migration/xbzrle.o
  CC      migration/block.o
  CC      net/net.o
  CC      net/queue.o
  CC      net/checksum.o
  CC      net/util.o
  CC      net/hub.o
  CC      net/socket.o
  CC      net/dump.o
  CC      net/eth.o
  CC      net/l2tpv3.o
  CC      net/tap.o
  CC      net/vhost-user.o
  CC      net/tap-linux.o
  CC      net/slirp.o
  CC      net/filter.o
  CC      net/filter-buffer.o
  CC      net/filter-mirror.o
  CC      net/colo-compare.o
  CC      net/colo.o
  CC      net/filter-rewriter.o
  CC      qom/cpu.o
  CC      net/filter-replay.o
  CC      replay/replay.o
  CC      replay/replay-internal.o
  CC      replay/replay-events.o
  CC      replay/replay-time.o
  CC      replay/replay-input.o
  CC      replay/replay-char.o
  CC      replay/replay-snapshot.o
  CC      replay/replay-net.o
  CC      replay/replay-audio.o
  CC      slirp/cksum.o
  CC      slirp/if.o
  CC      slirp/ip_icmp.o
  CC      slirp/ip6_icmp.o
  CC      slirp/ip6_output.o
  CC      slirp/ip_input.o
  CC      slirp/ip6_input.o
  CC      slirp/ip_output.o
  CC      slirp/dhcpv6.o
  CC      slirp/dnssearch.o
  CC      slirp/slirp.o
  CC      slirp/mbuf.o
  CC      slirp/misc.o
  CC      slirp/sbuf.o
  CC      slirp/socket.o
  CC      slirp/tcp_input.o
  CC      slirp/tcp_output.o
  CC      slirp/tcp_timer.o
  CC      slirp/tcp_subr.o
  CC      slirp/udp.o
  CC      slirp/udp6.o
  CC      slirp/bootp.o
  CC      slirp/tftp.o
  CC      slirp/arp_table.o
  CC      slirp/ndp_table.o
  CC      ui/keymaps.o
  CC      ui/console.o
  CC      ui/cursor.o
  CC      ui/qemu-pixman.o
  CC      ui/input.o
  CC      ui/input-keymap.o
  CC      ui/input-legacy.o
  CC      ui/input-linux.o
  CC      ui/spice-core.o
  CC      ui/spice-input.o
  CC      ui/spice-display.o
  CC      ui/sdl.o
  CC      ui/sdl_zoom.o
  CC      ui/x_keymap.o
  CC      ui/vnc.o
  CC      ui/vnc-enc-zlib.o
  CC      ui/vnc-enc-hextile.o
  CC      ui/vnc-enc-tight.o
  CC      ui/vnc-palette.o
  CC      ui/vnc-enc-zrle.o
  CC      ui/vnc-auth-vencrypt.o
  CC      ui/vnc-auth-sasl.o
  CC      ui/vnc-ws.o
  CC      ui/vnc-jobs.o
  CC      chardev/char.o
  CC      chardev/char-fd.o
  CC      chardev/char-file.o
  CC      chardev/char-io.o
  CC      chardev/char-mux.o
  CC      chardev/char-null.o
  CC      chardev/char-parallel.o
  CC      chardev/char-pipe.o
  CC      chardev/char-pty.o
  CC      chardev/char-ringbuf.o
  CC      chardev/char-serial.o
  CC      chardev/char-socket.o
  CC      chardev/char-stdio.o
  CC      chardev/char-udp.o
  CC      qom/object.o
  CC      qom/container.o
  CC      qom/qom-qobject.o
  CC      qom/object_interfaces.o
  LINK    tests/qemu-iotests/socket_scm_helper
  AS      optionrom/multiboot.o
  GEN     qemu-doc.html
  GEN     qemu-doc.txt
  AS      optionrom/linuxboot.o
  CC      optionrom/linuxboot_dma.o
  AS      optionrom/kvmvapic.o
  GEN     qemu.1
  BUILD   optionrom/multiboot.img
  BUILD   optionrom/linuxboot.img
  BUILD   optionrom/kvmvapic.img
  BUILD   optionrom/multiboot.raw
  BUILD   optionrom/kvmvapic.raw
  SIGN    optionrom/multiboot.bin
  GEN     qemu-img.1
  BUILD   optionrom/linuxboot.raw
  GEN     docs/qemu-qmp-ref.html
  BUILD   optionrom/linuxboot_dma.img
  SIGN    optionrom/linuxboot.bin
  SIGN    optionrom/kvmvapic.bin
  GEN     docs/qemu-qmp-ref.7
  BUILD   optionrom/linuxboot_dma.raw
  GEN     docs/qemu-qmp-ref.txt
  SIGN    optionrom/linuxboot_dma.bin
  GEN     docs/qemu-ga-ref.html
  GEN     docs/qemu-ga-ref.txt
  GEN     docs/qemu-ga-ref.7
  AR      libqemuutil.a
  AR      libqemustub.a
  LINK    fsdev/virtfs-proxy-helper
  LINK    qemu-bridge-helper
  PROTO   i386-softmmu/plog.proto 
  API     i386-softmmu/panda/plugins/osi/osi_ext.h 
  API     i386-softmmu/panda/plugins/callstack_instr/callstack_instr_ext.h 
  API     i386-softmmu/panda/plugins/wintrospection/wintrospection_ext.h 
  API     i386-softmmu/panda/plugins/osi_linux/osi_linux_ext.h 
  API     i386-softmmu/panda/plugins/libfi/libfi_ext.h 
  API     i386-softmmu/panda/plugins/winxpx86intro/winxpx86intro_ext.h 
  PROTO   x86_64-softmmu/plog.proto 
  API     x86_64-softmmu/panda/plugins/callstack_instr/callstack_instr_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  PROTO   ppc-softmmu/plog.proto 
  API     ppc-softmmu/panda/plugins/libfi/libfi_ext.h 
  PROTO   arm-softmmu/plog.proto 
WARNING: yacc table file version is out of date
  API     ppc-softmmu/panda/plugins/callstack_instr/callstack_instr_ext.h 
  API     arm-softmmu/panda/plugins/callstack_instr/callstack_instr_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  API     arm-softmmu/panda/plugins/libfi/libfi_ext.h 
  API     x86_64-softmmu/panda/plugins/libfi/libfi_ext.h 
  API     arm-softmmu/panda/plugins/osi/osi_ext.h 
  API     i386-softmmu/panda/plugins/win7x86intro/win7x86intro_ext.h 
  API     i386-softmmu/panda/plugins/win2000x86intro/win2000x86intro_ext.h 
  API     i386-softmmu/panda/plugins/syscalls2/syscalls2_ext.h 
  API     i386-softmmu/panda/plugins/pri/pri_ext.h 
  API     x86_64-softmmu/panda/plugins/osi/osi_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  API     arm-softmmu/panda/plugins/osi_linux/osi_linux_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  API     ppc-softmmu/panda/plugins/osi/osi_ext.h 
WARNING: yacc table file version is out of date
  API     arm-softmmu/panda/plugins/wintrospection/wintrospection_ext.h 
  API     ppc-softmmu/panda/plugins/osi_linux/osi_linux_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  API     arm-softmmu/panda/plugins/win7x86intro/win7x86intro_ext.h 
  API     i386-softmmu/panda/plugins/pri_dwarf/pri_dwarf_ext.h 
  API     arm-softmmu/panda/plugins/winxpx86intro/winxpx86intro_ext.h 
  API     i386-softmmu/panda/plugins/asid_instr_count/asid_instr_count_ext.h 
  API     x86_64-softmmu/panda/plugins/osi_linux/osi_linux_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  API     i386-softmmu/panda/plugins/mmio_trace/mmio_trace_ext.h 
WARNING: yacc table file version is out of date
  API     x86_64-softmmu/panda/plugins/wintrospection/wintrospection_ext.h 
  API     i386-softmmu/panda/plugins/taint2/taint2_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  API     arm-softmmu/panda/plugins/win2000x86intro/win2000x86intro_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  API     ppc-softmmu/panda/plugins/wintrospection/wintrospection_ext.h 
  API     arm-softmmu/panda/plugins/syscalls2/syscalls2_ext.h 
  API     ppc-softmmu/panda/plugins/winxpx86intro/winxpx86intro_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  API     i386-softmmu/panda/plugins/tainted_branch/tainted_branch_ext.h 
  API     arm-softmmu/panda/plugins/pri/pri_ext.h 
  GEN     i386-softmmu/hmp-commands.h
  API     arm-softmmu/panda/plugins/pri_dwarf/pri_dwarf_ext.h 
  API     x86_64-softmmu/panda/plugins/winxpx86intro/winxpx86intro_ext.h 
WARNING: yacc table file version is out of date
  GEN     i386-softmmu/hmp-commands-info.h
WARNING: yacc table file version is out of date
  GEN     i386-softmmu/config-target.h
# C protobuf
  PROTO   i386-softmmu/plog.pb-c.h i386-softmmu/plog.pb-c.c 
# C++ Protobuf 
  PROTO   i386-softmmu/plog.pb.h
  i386-softmmu/plog.pb.cc 
  API     arm-softmmu/panda/plugins/asid_instr_count/asid_instr_count_ext.h 
  API     x86_64-softmmu/panda/plugins/win7x86intro/win7x86intro_ext.h 
  API     x86_64-softmmu/panda/plugins/win2000x86intro/win2000x86intro_ext.h 
  API     arm-softmmu/panda/plugins/mmio_trace/mmio_trace_ext.h 
  API     ppc-softmmu/panda/plugins/win7x86intro/win7x86intro_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  API     arm-softmmu/panda/plugins/taint2/taint2_ext.h 
  API     ppc-softmmu/panda/plugins/win2000x86intro/win2000x86intro_ext.h 
  API     arm-softmmu/panda/plugins/tainted_branch/tainted_branch_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  CC      i386-softmmu/panda/src/callbacks.o
  GEN     arm-softmmu/hmp-commands.h
  GEN     arm-softmmu/hmp-commands-info.h
  GEN     arm-softmmu/config-target.h
# C protobuf
  PROTO   arm-softmmu/plog.pb-c.h arm-softmmu/plog.pb-c.c 
# C++ Protobuf 
  PROTO   arm-softmmu/plog.pb.h
  arm-softmmu/plog.pb.cc 
  API     x86_64-softmmu/panda/plugins/syscalls2/syscalls2_ext.h 
  API     ppc-softmmu/panda/plugins/syscalls2/syscalls2_ext.h 
  API     x86_64-softmmu/panda/plugins/pri/pri_ext.h 
  API     ppc-softmmu/panda/plugins/pri/pri_ext.h 
  API     x86_64-softmmu/panda/plugins/pri_dwarf/pri_dwarf_ext.h 
  API     x86_64-softmmu/panda/plugins/asid_instr_count/asid_instr_count_ext.h 
WARNING: yacc table file version is out of date
  API     x86_64-softmmu/panda/plugins/mmio_trace/mmio_trace_ext.h 
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  API     ppc-softmmu/panda/plugins/pri_dwarf/pri_dwarf_ext.h 
WARNING: yacc table file version is out of date
  API     x86_64-softmmu/panda/plugins/taint2/taint2_ext.h 
WARNING: yacc table file version is out of date
  API     ppc-softmmu/panda/plugins/asid_instr_count/asid_instr_count_ext.h 
  CC      arm-softmmu/panda/src/callbacks.o
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
WARNING: yacc table file version is out of date
  CC      i386-softmmu/panda/src/callback_support.o
  CC      arm-softmmu/panda/src/callback_support.o
  API     ppc-softmmu/panda/plugins/mmio_trace/mmio_trace_ext.h 
  API     x86_64-softmmu/panda/plugins/tainted_branch/tainted_branch_ext.h 
  GEN     x86_64-softmmu/hmp-commands.h
  CC      i386-softmmu/panda/src/common.o
WARNING: yacc table file version is out of date
  GEN     x86_64-softmmu/hmp-commands-info.h
  GEN     x86_64-softmmu/config-target.h
# C protobuf
# C++ Protobuf 
  PROTO   x86_64-softmmu/plog.pb.h
  x86_64-softmmu/plog.pb.cc 
  PROTO   x86_64-softmmu/plog.pb-c.h x86_64-softmmu/plog.pb-c.c 
WARNING: yacc table file version is out of date
  API     ppc-softmmu/panda/plugins/taint2/taint2_ext.h 
  CC      i386-softmmu/panda/src/plog.o
  CC      i386-softmmu/plog.pb-c.o
  CC      arm-softmmu/panda/src/common.o
  API     ppc-softmmu/panda/plugins/tainted_branch/tainted_branch_ext.h 
  GEN     ppc-softmmu/hmp-commands.h
  GEN     ppc-softmmu/hmp-commands-info.h
WARNING: yacc table file version is out of date
# C protobuf
  GEN     ppc-softmmu/config-target.h
  PROTO   ppc-softmmu/plog.pb-c.h ppc-softmmu/plog.pb-c.c 
  CC      i386-softmmu/panda/src/rr/rr_log.o
  CC      i386-softmmu/panda/src/checkpoint.o
WARNING: yacc table file version is out of date
  CXX     i386-softmmu/panda/src/plog-cc.o
  CC      arm-softmmu/panda/src/plog.o
  CXX     i386-softmmu/plog.pb.o
  CC      arm-softmmu/plog.pb-c.o
  CXX     i386-softmmu/panda/llvm/tcg-llvm.o
  CXX     i386-softmmu/panda/llvm/helper_runtime.o
  CC      arm-softmmu/panda/src/rr/rr_log.o
# C++ Protobuf 
  PROTO   ppc-softmmu/plog.pb.h
  ppc-softmmu/plog.pb.cc 
  CC      arm-softmmu/panda/src/checkpoint.o
  CXX     arm-softmmu/panda/src/plog-cc.o
  CC      i386-softmmu/exec.o
  CC      x86_64-softmmu/panda/src/callbacks.o
  CXX     arm-softmmu/plog.pb.o
  CC      i386-softmmu/translate-all.o
  CC      ppc-softmmu/panda/src/callbacks.o
  CC      x86_64-softmmu/panda/src/callback_support.o
  CC      i386-softmmu/cpu-exec.o
  CC      i386-softmmu/translate-common.o
  CC      ppc-softmmu/panda/src/callback_support.o
  CC      i386-softmmu/cpu-exec-common.o
  CC      i386-softmmu/tcg/tcg.o
  CC      x86_64-softmmu/panda/src/common.o
  CC      i386-softmmu/tcg/tcg-op.o
  CXX     arm-softmmu/panda/llvm/tcg-llvm.o
  CC      ppc-softmmu/panda/src/common.o
  CC      i386-softmmu/tcg/optimize.o
  CC      x86_64-softmmu/panda/src/plog.o
  CXX     arm-softmmu/panda/llvm/helper_runtime.o
  CC      ppc-softmmu/panda/src/plog.o
  CC      x86_64-softmmu/plog.pb-c.o
  CC      ppc-softmmu/plog.pb-c.o
  CC      x86_64-softmmu/panda/src/rr/rr_log.o
  CC      ppc-softmmu/panda/src/rr/rr_log.o
  CC      i386-softmmu/tcg/tcg-common.o
  CC      i386-softmmu/fpu/softfloat.o
  CC      i386-softmmu/disas.o
  CC      i386-softmmu/tcg-runtime.o
  GEN     i386-softmmu/gdbstub-xml.c
  CC      i386-softmmu/hax-stub.o
  CC      i386-softmmu/arch_init.o
  CC      i386-softmmu/cpus.o
  CC      i386-softmmu/monitor.o
  CC      i386-softmmu/gdbstub.o
  CC      x86_64-softmmu/panda/src/checkpoint.o
  CC      i386-softmmu/balloon.o
  CC      ppc-softmmu/panda/src/checkpoint.o
  CXX     x86_64-softmmu/panda/src/plog-cc.o
  CC      i386-softmmu/ioport.o
  CC      i386-softmmu/numa.o
  CXX     ppc-softmmu/panda/src/plog-cc.o
  CC      i386-softmmu/qtest.o
  CC      arm-softmmu/exec.o
  CC      i386-softmmu/bootdevice.o
  CC      i386-softmmu/kvm-all.o
  CC      i386-softmmu/memory.o
  CC      i386-softmmu/cputlb.o
  CC      i386-softmmu/memory_mapping.o
  CC      i386-softmmu/dump.o
  CXX     x86_64-softmmu/plog.pb.o
  CC      i386-softmmu/migration/ram.o
  CXX     ppc-softmmu/plog.pb.o
  CC      i386-softmmu/migration/savevm.o
  CC      i386-softmmu/xen-common.o
  CC      i386-softmmu/xen-hvm.o
  CC      i386-softmmu/xen-mapcache.o
  CC      i386-softmmu/hw/9pfs/virtio-9p-device.o
  CC      i386-softmmu/hw/block/virtio-blk.o
  CC      i386-softmmu/hw/block/dataplane/virtio-blk.o
  CC      i386-softmmu/hw/char/virtio-serial-bus.o
  CC      i386-softmmu/hw/core/nmi.o
  CC      i386-softmmu/hw/core/generic-loader.o
  CC      i386-softmmu/hw/core/null-machine.o
  CC      i386-softmmu/hw/cpu/core.o
  CC      arm-softmmu/translate-all.o
  CC      i386-softmmu/hw/display/vga.o
  CC      i386-softmmu/hw/display/virtio-gpu.o
  CC      i386-softmmu/hw/display/virtio-gpu-3d.o
  CC      i386-softmmu/hw/display/virtio-gpu-pci.o
  CC      i386-softmmu/hw/display/virtio-vga.o
  CC      arm-softmmu/cpu-exec.o
  CC      i386-softmmu/hw/intc/apic.o
  CC      i386-softmmu/hw/intc/apic_common.o
  CC      i386-softmmu/hw/intc/ioapic.o
  CC      arm-softmmu/translate-common.o
  CC      i386-softmmu/hw/isa/lpc_ich9.o
  CC      i386-softmmu/hw/misc/vmport.o
  CC      arm-softmmu/cpu-exec-common.o
  CC      i386-softmmu/hw/misc/ivshmem.o
  CC      i386-softmmu/hw/misc/pvpanic.o
  CC      i386-softmmu/hw/misc/edu.o
  CC      i386-softmmu/hw/misc/hyperv_testdev.o
  CC      arm-softmmu/tcg/tcg.o
  CC      arm-softmmu/tcg/tcg-op.o
  CC      i386-softmmu/hw/net/virtio-net.o
  CC      i386-softmmu/hw/net/vhost_net.o
  CC      i386-softmmu/hw/scsi/virtio-scsi.o
  CC      i386-softmmu/hw/scsi/virtio-scsi-dataplane.o
  CC      i386-softmmu/hw/scsi/vhost-scsi.o
  CC      i386-softmmu/hw/timer/mc146818rtc.o
  CC      i386-softmmu/hw/vfio/common.o
  CC      i386-softmmu/hw/vfio/pci.o
  CC      i386-softmmu/hw/vfio/platform.o
  CC      i386-softmmu/hw/vfio/pci-quirks.o
  CC      i386-softmmu/hw/vfio/spapr.o
  CC      arm-softmmu/tcg/optimize.o
  CC      i386-softmmu/hw/virtio/virtio.o
  CC      i386-softmmu/hw/virtio/virtio-balloon.o
  CC      i386-softmmu/hw/virtio/vhost.o
  CC      i386-softmmu/hw/virtio/vhost-backend.o
  CC      i386-softmmu/hw/virtio/vhost-user.o
  CC      i386-softmmu/hw/virtio/vhost-vsock.o
  CC      i386-softmmu/hw/virtio/virtio-crypto.o
  CC      i386-softmmu/hw/virtio/virtio-crypto-pci.o
  CC      i386-softmmu/hw/xen/xen-host-pci-device.o
  CC      i386-softmmu/hw/xen/xen_pt.o
  CC      i386-softmmu/hw/xen/xen_pt_config_init.o
  CC      i386-softmmu/hw/xen/xen_pt_graphics.o
  CC      i386-softmmu/hw/xen/xen_pt_msi.o
  CC      i386-softmmu/hw/i386/multiboot.o
  CC      i386-softmmu/hw/i386/pc.o
  CC      arm-softmmu/tcg/tcg-common.o
  CC      i386-softmmu/hw/i386/pc_piix.o
  CC      i386-softmmu/hw/i386/pc_q35.o
  CC      i386-softmmu/hw/i386/pc_sysfw.o
  CC      i386-softmmu/hw/i386/x86-iommu.o
  CC      arm-softmmu/fpu/softfloat.o
  CC      i386-softmmu/hw/i386/intel_iommu.o
  CC      i386-softmmu/hw/i386/amd_iommu.o
  CC      arm-softmmu/disas.o
  CC      i386-softmmu/hw/i386/kvmvapic.o
  CC      i386-softmmu/hw/i386/acpi-build.o
  CC      i386-softmmu/hw/i386/pci-assign-load-rom.o
  CC      arm-softmmu/tcg-runtime.o
  CC      i386-softmmu/hw/i386/../xenpv/xen_machine_pv.o
  CC      i386-softmmu/hw/i386/kvm/clock.o
  CC      i386-softmmu/hw/i386/kvm/apic.o
  CC      i386-softmmu/hw/i386/kvm/i8259.o
  CC      i386-softmmu/hw/i386/kvm/ioapic.o
  GEN     arm-softmmu/gdbstub-xml.c
  CC      arm-softmmu/hax-stub.o
  CC      i386-softmmu/hw/i386/kvm/i8254.o
  CC      arm-softmmu/kvm-stub.o
  CC      i386-softmmu/hw/i386/kvm/pci-assign.o
  CC      i386-softmmu/hw/i386/xen/xen_platform.o
  CC      i386-softmmu/hw/i386/xen/xen_apic.o
  CC      i386-softmmu/hw/i386/xen/xen_pvdevice.o
  CC      arm-softmmu/arch_init.o
  CC      i386-softmmu/target/i386/translate.o
  CC      i386-softmmu/target/i386/helper.o
  CC      i386-softmmu/target/i386/cpu.o
  CC      i386-softmmu/target/i386/bpt_helper.o
  CC      i386-softmmu/target/i386/excp_helper.o
  CC      arm-softmmu/cpus.o
  CC      i386-softmmu/target/i386/fpu_helper.o
  CC      i386-softmmu/target/i386/cc_helper.o
  CC      i386-softmmu/target/i386/int_helper.o
  CC      i386-softmmu/target/i386/svm_helper.o
  CC      i386-softmmu/target/i386/smm_helper.o
  CC      i386-softmmu/target/i386/misc_helper.o
  CC      i386-softmmu/target/i386/mem_helper.o
  CC      i386-softmmu/target/i386/seg_helper.o
  CC      arm-softmmu/monitor.o
  CC      i386-softmmu/target/i386/mpx_helper.o
  CC      i386-softmmu/target/i386/gdbstub.o
  CC      i386-softmmu/target/i386/machine.o
  CC      i386-softmmu/target/i386/arch_memory_mapping.o
  CC      i386-softmmu/target/i386/arch_dump.o
  CXX     ppc-softmmu/panda/llvm/tcg-llvm.o
  CC      i386-softmmu/target/i386/monitor.o
  CC      i386-softmmu/target/i386/kvm.o
  CC      i386-softmmu/target/i386/hyperv.o
  GEN     trace/generated-helpers.c
  CC      i386-softmmu/trace/control-target.o
  CC      i386-softmmu/panda/src/rr/rr_print.o
  CXX     x86_64-softmmu/panda/llvm/tcg-llvm.o
  PROTO   i386-softmmu/plog_pb2.py 
  CC      i386-softmmu/panda/src/rr/rr_rmvapic.o
  CXX     ppc-softmmu/panda/llvm/helper_runtime.o
  CXX     i386-softmmu/panda/src/plog_reader.o
  CXX     i386-softmmu/panda/plugins/asidstory/asidstory.o
  CXX     i386-softmmu/panda/plugins/callstack_instr/callstack_instr.o
  CC      arm-softmmu/gdbstub.o
  CC      arm-softmmu/balloon.o
  CC      i386-softmmu/panda/plugins/checkpoint/checkpoint.o
  CC      arm-softmmu/ioport.o
  PLUGIN  i386-softmmu/panda/plugins/panda_checkpoint.so 
  CC      arm-softmmu/numa.o
  CXX     i386-softmmu/panda/plugins/libfi/libfi.o
  CC      arm-softmmu/qtest.o
  CC      arm-softmmu/bootdevice.o
  CXX     x86_64-softmmu/panda/llvm/helper_runtime.o
  CXX     i386-softmmu/panda/plugins/loaded/loaded.o
  CC      arm-softmmu/memory.o
  CC      i386-softmmu/panda/plugins/osi/os_intro.o
  PLUGIN  i386-softmmu/panda/plugins/panda_callstack_instr.so 
  CC      i386-softmmu/panda/plugins/osi_test/osi_test.o
  PLUGIN  i386-softmmu/panda/plugins/panda_osi.so 
  CXX     i386-softmmu/panda/plugins/osi_linux/osi_linux.o
  CC      i386-softmmu/panda/plugins/wintrospection/wintrospection.o
  PLUGIN  i386-softmmu/panda/plugins/panda_osi_test.so 
  CC      ppc-softmmu/exec.o
  PLUGIN  i386-softmmu/panda/plugins/panda_loaded.so 
  CXX     i386-softmmu/panda/plugins/winxpx86intro/winxpx86intro.o
  PLUGIN  i386-softmmu/panda/plugins/panda_libfi.so 
  CXX     i386-softmmu/panda/plugins/win7x86intro/win7x86intro.o
  CXX     i386-softmmu/panda/plugins/win2000x86intro/win2000x86intro.o
  PLUGIN  i386-softmmu/panda/plugins/panda_winxpx86intro.so 
  CXX     i386-softmmu/panda/plugins/syscalls2/syscalls2.o
  PLUGIN  i386-softmmu/panda/plugins/panda_win7x86intro.so 
  CC      arm-softmmu/cputlb.o
  PLUGIN  i386-softmmu/panda/plugins/panda_win2000x86intro.so 
  PLUGIN  i386-softmmu/panda/plugins/panda_wintrospection.so 
  CC      i386-softmmu/panda/plugins/pri/pri.o
  CXX     i386-softmmu/panda/plugins/pri_dwarf/pri_dwarf.o
  CXX     i386-softmmu/panda/plugins/pri_simple/pri_simple.o
  UTIL CC i386-softmmu/panda/plugins/osi_linux/kernelinfo_read.o 
  PLUGIN  i386-softmmu/panda/plugins/panda_pri.so 
  CXX     i386-softmmu/panda/plugins/osi_linux/default_profile.o
  PLUGIN  i386-softmmu/panda/plugins/panda_asidstory.so 
  CC      i386-softmmu/panda/plugins/scissors/scissors.o
  PLUGIN  i386-softmmu/panda/plugins/panda_pri_simple.so 
  CXX     i386-softmmu/panda/plugins/stringsearch/stringsearch.o
  CXX     i386-softmmu/panda/plugins/asid_instr_count/asid_instr_count.o
  CXX     i386-softmmu/panda/plugins/osi_linux/kernel_2_4_x_profile.o
  PLUGIN  i386-softmmu/panda/plugins/panda_scissors.so 
  CC      x86_64-softmmu/exec.o
  CC      i386-softmmu/panda/plugins/replaymovie/replaymovie.o
  PLUGIN  i386-softmmu/panda/plugins/panda_replaymovie.so 
  CP      i386-softmmu/panda/plugins/osi_linux/kernelinfo.conf 
  PLUGIN  i386-softmmu/panda/plugins/panda_osi_linux.so 
  CC      x86_64-softmmu/translate-all.o
  CC      i386-softmmu/panda/plugins/memsavep/memsavep.o
  CC      ppc-softmmu/translate-all.o
  PLUGIN  i386-softmmu/panda/plugins/panda_asid_instr_count.so 
  PLUGIN  i386-softmmu/panda/plugins/panda_memsavep.so 
  CXX     i386-softmmu/panda/plugins/unigrams/unigrams.o
  CC      ppc-softmmu/cpu-exec.o
  CXX     i386-softmmu/panda/plugins/textprinter/textprinter.o
  CC      x86_64-softmmu/cpu-exec.o
  PLUGIN  i386-softmmu/panda/plugins/panda_stringsearch.so 
  CC      x86_64-softmmu/translate-common.o
  CC      arm-softmmu/memory_mapping.o
  CC      ppc-softmmu/translate-common.o
  CXX     i386-softmmu/panda/plugins/net/net.o
  CC      x86_64-softmmu/cpu-exec-common.o
  CC      ppc-softmmu/cpu-exec-common.o
  CC      ppc-softmmu/tcg/tcg.o
  CC      arm-softmmu/dump.o
  CC      x86_64-softmmu/tcg/tcg.o
  PLUGIN  i386-softmmu/panda/plugins/panda_net.so 
  CC      x86_64-softmmu/tcg/tcg-op.o
  CC      ppc-softmmu/tcg/tcg-op.o
  CXX     i386-softmmu/panda/plugins/network/network.o
  PLUGIN  i386-softmmu/panda/plugins/panda_unigrams.so 
  PLUGIN  i386-softmmu/panda/plugins/panda_textprinter.so 
  CXX     i386-softmmu/panda/plugins/filereadmon/filereadmon.o
  CXX     i386-softmmu/panda/plugins/callfunc/callfunc.o
  PLUGIN  i386-softmmu/panda/plugins/panda_network.so 
  CXX     i386-softmmu/panda/plugins/mmio_trace/mmio_trace.o
  CXX     i386-softmmu/panda/plugins/file_taint/file_taint.o
  CC      arm-softmmu/migration/ram.o
  CC      x86_64-softmmu/tcg/optimize.o
  PLUGIN  i386-softmmu/panda/plugins/panda_mmio_trace.so 
  CXX     i386-softmmu/panda/plugins/pri_taint/pri_taint.o
  PLUGIN  i386-softmmu/panda/plugins/panda_filereadmon.so 
  PLUGIN  i386-softmmu/panda/plugins/panda_file_taint.so 
  CC      arm-softmmu/migration/savevm.o
  PLUGIN  i386-softmmu/panda/plugins/panda_callfunc.so 
  CXX     i386-softmmu/panda/plugins/taint2/label_set.o
  CXX     i386-softmmu/panda/plugins/pri_trace/pri_trace.o
  CC      x86_64-softmmu/tcg/tcg-common.o
  CXX     i386-softmmu/panda/plugins/tainted_branch/tainted_branch.o
  CC      ppc-softmmu/tcg/optimize.o
  CC      i386-softmmu/panda/plugins/syscalls2/syscalls2_info.o
  CC      x86_64-softmmu/fpu/softfloat.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_2000_x86.o
  CC      ppc-softmmu/tcg/tcg-common.o
  CC      arm-softmmu/xen-common-stub.o
  CC      x86_64-softmmu/disas.o
  PLUGIN  i386-softmmu/panda/plugins/panda_pri_trace.so 
  CXX     i386-softmmu/panda/plugins/taint2/shad_dir_32.o
  CC      ppc-softmmu/fpu/softfloat.o
  CC      arm-softmmu/xen-hvm-stub.o
  CXX     i386-softmmu/panda/plugins/tstringsearch/tstringsearch.o
  PLUGIN  i386-softmmu/panda/plugins/panda_pri_taint.so 
  CXX     i386-softmmu/panda/plugins/taint2/taint_ops.o
  CC      x86_64-softmmu/tcg-runtime.o
  CC      arm-softmmu/hw/9pfs/virtio-9p-device.o
  CXX     i386-softmmu/panda/plugins/tainted_instr/tainted_instr.o
  CC      ppc-softmmu/disas.o
  GEN     x86_64-softmmu/gdbstub-xml.c
  CC      arm-softmmu/hw/adc/stm32f2xx_adc.o
  CC      x86_64-softmmu/hax-stub.o
  CC      ppc-softmmu/tcg-runtime.o
  CC      x86_64-softmmu/arch_init.o
  CC      arm-softmmu/hw/block/virtio-blk.o
  PLUGIN  i386-softmmu/panda/plugins/panda_tainted_branch.so 
  GEN     ppc-softmmu/gdbstub-xml.c
  CC      ppc-softmmu/hax-stub.o
  CXX     i386-softmmu/panda/plugins/ida_taint2/ida_taint2.o
  PLUGIN  i386-softmmu/panda/plugins/panda_pri_dwarf.so 
  CC      ppc-softmmu/kvm-stub.o
  CC      ppc-softmmu/libdecnumber/decContext.o
  PLUGIN  i386-softmmu/panda/plugins/panda_tstringsearch.so 
  CXX     i386-softmmu/panda/plugins/tainted_net/tainted_net.o
  CC      arm-softmmu/hw/block/dataplane/virtio-blk.o
  CC      ppc-softmmu/libdecnumber/decNumber.o
  CC      ppc-softmmu/libdecnumber/dpd/decimal32.o
  PLUGIN  i386-softmmu/panda/plugins/panda_tainted_instr.so 
  CC      arm-softmmu/hw/char/exynos4210_uart.o
  CC      arm-softmmu/hw/char/omap_uart.o
  CC      ppc-softmmu/libdecnumber/dpd/decimal64.o
  CXX     i386-softmmu/panda/plugins/serial_taint/serial_taint.o
  CC      arm-softmmu/hw/char/stm32f2xx_usart.o
  CC      arm-softmmu/hw/char/digic-uart.o
  CXX     i386-softmmu/panda/plugins/taint2/taint2.o
  PLUGIN  i386-softmmu/panda/plugins/panda_ida_taint2.so 
  CC      ppc-softmmu/libdecnumber/dpd/decimal128.o
  CC      arm-softmmu/hw/char/virtio-serial-bus.o
  CC      arm-softmmu/hw/char/bcm2835_aux.o
  CLANG   i386-softmmu/fpu/softfloat.bc2 
  CC      x86_64-softmmu/cpus.o
  CC      ppc-softmmu/arch_init.o
  CC      arm-softmmu/hw/core/nmi.o
  CC      arm-softmmu/hw/core/generic-loader.o
  PLUGIN  i386-softmmu/panda/plugins/panda_tainted_net.so 
  CC      ppc-softmmu/cpus.o
  CLANG   i386-softmmu/target/i386/helper.bc2 
  CC      arm-softmmu/hw/core/null-machine.o
  CC      arm-softmmu/hw/cpu/arm11mpcore.o
  CLANG   i386-softmmu/target/i386/bpt_helper.bc2 
  CC      x86_64-softmmu/monitor.o
  CC      ppc-softmmu/monitor.o
  CLANG   i386-softmmu/target/i386/excp_helper.bc2 
  CC      arm-softmmu/hw/cpu/realview_mpcore.o
  PLUGIN  i386-softmmu/panda/plugins/panda_serial_taint.so 
  CC      arm-softmmu/hw/cpu/a9mpcore.o
  CLANG   i386-softmmu/target/i386/fpu_helper.bc2 
  CLANG   i386-softmmu/target/i386/cc_helper.bc2 
  CLANG   i386-softmmu/target/i386/int_helper.bc2 
  CC      arm-softmmu/hw/cpu/a15mpcore.o
  CC      arm-softmmu/hw/cpu/core.o
  CC      ppc-softmmu/gdbstub.o
  CLANG   i386-softmmu/target/i386/svm_helper.bc2 
  CC      ppc-softmmu/balloon.o
  CLANG   i386-softmmu/target/i386/smm_helper.bc2 
  CC      arm-softmmu/hw/display/omap_dss.o
  CC      ppc-softmmu/ioport.o
  CC      ppc-softmmu/numa.o
  CLANG   i386-softmmu/target/i386/misc_helper.bc2 
  CLANG   i386-softmmu/target/i386/mem_helper.bc2 
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_7_x86.o
  CC      ppc-softmmu/qtest.o
  CC      arm-softmmu/hw/display/omap_lcdc.o
  CLANG   i386-softmmu/target/i386/seg_helper.bc2 
  CLANG   i386-softmmu/target/i386/mpx_helper.bc2 
  CC      i386-softmmu/gdbstub-xml.o
  CC      ppc-softmmu/bootdevice.o
  LINK    i386-softmmu/rr_print_i386
  CC      arm-softmmu/hw/display/pxa2xx_lcd.o
  LINK    i386-softmmu/rr_rmvapic_i386
  CC      ppc-softmmu/memory.o
  CC      ppc-softmmu/cputlb.o
  CXX     i386-softmmu/panda/tools/helper_call_modifier.o
  LINK    i386-softmmu/plog_reader
  CC      ppc-softmmu/memory_mapping.o
  CC      x86_64-softmmu/gdbstub.o
  CXX     i386-softmmu/panda/plugins/taint2/shad_dir_64.o
  CC      i386-softmmu/trace/generated-helpers.o
  LLVMLD  i386-softmmu/llvm-helpers.bc1 
  CC      ppc-softmmu/dump.o
  CC      ppc-softmmu/migration/ram.o
  CC      arm-softmmu/hw/display/bcm2835_fb.o
  CC      x86_64-softmmu/balloon.o
  CXX     i386-softmmu/panda/plugins/taint2/taint_api.o
  CC      x86_64-softmmu/ioport.o
  CC      arm-softmmu/hw/display/vga.o
  CC      arm-softmmu/hw/display/virtio-gpu.o
  CC      x86_64-softmmu/numa.o
  CC      ppc-softmmu/migration/savevm.o
  CC      x86_64-softmmu/qtest.o
  CC      ppc-softmmu/xen-common-stub.o
  CC      x86_64-softmmu/bootdevice.o
  CC      ppc-softmmu/xen-hvm-stub.o
  CC      ppc-softmmu/hw/9pfs/virtio-9p-device.o
  CC      ppc-softmmu/hw/block/virtio-blk.o
  CC      x86_64-softmmu/kvm-all.o
  CC      x86_64-softmmu/memory.o
  CC      ppc-softmmu/hw/block/dataplane/virtio-blk.o
  CC      arm-softmmu/hw/display/virtio-gpu-3d.o
  CC      arm-softmmu/hw/display/virtio-gpu-pci.o
  CC      ppc-softmmu/hw/char/virtio-serial-bus.o
  CC      arm-softmmu/hw/dma/omap_dma.o
  CC      ppc-softmmu/hw/core/nmi.o
  CC      ppc-softmmu/hw/core/generic-loader.o
  CC      arm-softmmu/hw/dma/soc_dma.o
  CC      ppc-softmmu/hw/core/null-machine.o
  CXX     i386-softmmu/panda/plugins/taint2/shad.o
  CC      ppc-softmmu/hw/cpu/core.o
  CC      ppc-softmmu/hw/display/vga.o
  CC      arm-softmmu/hw/dma/pxa2xx_dma.o
  CC      ppc-softmmu/hw/display/virtio-gpu.o
  CC      ppc-softmmu/hw/display/virtio-gpu-3d.o
  CC      ppc-softmmu/hw/display/virtio-gpu-pci.o
  CC      arm-softmmu/hw/dma/bcm2835_dma.o
  CC      ppc-softmmu/hw/misc/ivshmem.o
  CC      x86_64-softmmu/cputlb.o
  CC      arm-softmmu/hw/gpio/omap_gpio.o
  CC      ppc-softmmu/hw/misc/edu.o
  CC      arm-softmmu/hw/gpio/imx_gpio.o
  LINK    i386-softmmu/qemu-system-i386
  CC      ppc-softmmu/hw/net/xilinx_ethlite.o
  CC      ppc-softmmu/hw/net/virtio-net.o
  CC      ppc-softmmu/hw/net/vhost_net.o
  CC      arm-softmmu/hw/gpio/bcm2835_gpio.o
  CC      x86_64-softmmu/memory_mapping.o
  CC      ppc-softmmu/hw/net/fsl_etsec/etsec.o
  CC      ppc-softmmu/hw/net/fsl_etsec/registers.o
  CC      ppc-softmmu/hw/net/fsl_etsec/rings.o
  CC      arm-softmmu/hw/i2c/omap_i2c.o
  CC      x86_64-softmmu/dump.o
  CXX     i386-softmmu/panda/plugins/taint2/llvm_taint_lib.o
  CC      ppc-softmmu/hw/net/fsl_etsec/miim.o
  CC      ppc-softmmu/hw/scsi/virtio-scsi.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_7_x86.o
  CC      ppc-softmmu/hw/scsi/virtio-scsi-dataplane.o
  CC      ppc-softmmu/hw/scsi/vhost-scsi.o
  CC      arm-softmmu/hw/input/pxa2xx_keypad.o
  CC      ppc-softmmu/hw/timer/mc146818rtc.o
  CC      ppc-softmmu/hw/vfio/common.o
  CC      ppc-softmmu/hw/vfio/pci.o
  CC      arm-softmmu/hw/input/tsc210x.o
  CC      ppc-softmmu/hw/vfio/pci-quirks.o
  CC      x86_64-softmmu/migration/ram.o
  CC      ppc-softmmu/hw/vfio/platform.o
  CC      arm-softmmu/hw/intc/armv7m_nvic.o
  CC      x86_64-softmmu/migration/savevm.o
  CC      ppc-softmmu/hw/vfio/spapr.o
  CC      ppc-softmmu/hw/virtio/virtio.o
  CC      ppc-softmmu/hw/virtio/virtio-balloon.o
  CC      ppc-softmmu/hw/virtio/vhost.o
  CC      arm-softmmu/hw/intc/exynos4210_gic.o
  CC      ppc-softmmu/hw/virtio/vhost-backend.o
  CC      x86_64-softmmu/xen-common.o
  CC      arm-softmmu/hw/intc/exynos4210_combiner.o
  CC      ppc-softmmu/hw/virtio/vhost-user.o
  CC      ppc-softmmu/hw/virtio/vhost-vsock.o
  CC      arm-softmmu/hw/intc/omap_intc.o
  CC      x86_64-softmmu/xen-hvm.o
  CC      x86_64-softmmu/xen-mapcache.o
  CC      ppc-softmmu/hw/virtio/virtio-crypto.o
  CC      ppc-softmmu/hw/virtio/virtio-crypto-pci.o
  CC      ppc-softmmu/hw/ppc/ppc.o
  CC      ppc-softmmu/hw/ppc/ppc_booke.o
  CC      ppc-softmmu/hw/ppc/fdt.o
  CC      x86_64-softmmu/hw/9pfs/virtio-9p-device.o
  CC      ppc-softmmu/hw/ppc/ppc405_boards.o
  CXX     i386-softmmu/panda/plugins/taint2/taint2_hypercalls.o
  CC      arm-softmmu/hw/intc/bcm2835_ic.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_xpsp3_x86.o
  CC      x86_64-softmmu/hw/block/virtio-blk.o
  CC      arm-softmmu/hw/intc/bcm2836_control.o
  CC      x86_64-softmmu/hw/block/dataplane/virtio-blk.o
  CC      ppc-softmmu/hw/ppc/ppc4xx_devs.o
  CC      x86_64-softmmu/hw/char/virtio-serial-bus.o
  CC      ppc-softmmu/hw/ppc/ppc405_uc.o
  CC      ppc-softmmu/hw/ppc/ppc440_bamboo.o
  CC      arm-softmmu/hw/intc/allwinner-a10-pic.o
  CC      x86_64-softmmu/hw/core/nmi.o
  CC      ppc-softmmu/hw/ppc/ppc4xx_pci.o
  LINK    i386-softmmu/panda/tools/helper_call_modifier
  CC      x86_64-softmmu/hw/core/generic-loader.o
  CC      arm-softmmu/hw/intc/aspeed_vic.o
  CC      arm-softmmu/hw/intc/arm_gicv3_cpuif.o
  CC      ppc-softmmu/hw/ppc/prep.o
  CC      ppc-softmmu/hw/ppc/prep_systemio.o
  CLANGXX i386-softmmu/panda/plugins/taint2/taint_ops_llvm.bc 
  CC      ppc-softmmu/hw/ppc/rs6000_mc.o
  CC      x86_64-softmmu/hw/core/null-machine.o
  CC      arm-softmmu/hw/misc/ivshmem.o
  CC      ppc-softmmu/hw/ppc/mac_oldworld.o
  CC      ppc-softmmu/hw/ppc/mac_newworld.o
  CC      x86_64-softmmu/hw/cpu/core.o
  LLMORPH i386-softmmu/llvm-helpers.bc 
  CC      ppc-softmmu/hw/ppc/e500.o
  CC      ppc-softmmu/hw/ppc/mpc8544ds.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_linux_arm.o
  CC      x86_64-softmmu/hw/display/vga.o
  CC      ppc-softmmu/hw/ppc/e500plat.o
  CC      ppc-softmmu/hw/ppc/mpc8544_guts.o
  PLUGIN  i386-softmmu/panda/plugins/panda_taint2.so 
  CC      arm-softmmu/hw/misc/arm_sysctl.o
  CC      ppc-softmmu/hw/ppc/ppce500_spin.o
  CC      ppc-softmmu/hw/ppc/virtex_ml507.o
  CC      ppc-softmmu/target/ppc/cpu-models.o
  CC      arm-softmmu/hw/misc/cbus.o
  CC      x86_64-softmmu/hw/display/virtio-gpu.o
  CC      ppc-softmmu/target/ppc/cpu.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_xpsp3_x86.o
  CC      ppc-softmmu/target/ppc/translate.o
  CC      ppc-softmmu/target/ppc/machine.o
  CC      arm-softmmu/hw/misc/exynos4210_pmu.o
  CC      arm-softmmu/hw/misc/exynos4210_clk.o
  LLVMLD  i386-softmmu/panda/plugins/panda_taint2_ops.bc 
  CC      arm-softmmu/hw/misc/imx_ccm.o
  CC      arm-softmmu/hw/misc/imx31_ccm.o
  CC      arm-softmmu/hw/misc/imx25_ccm.o
  CC      ppc-softmmu/target/ppc/mmu_helper.o
  CC      arm-softmmu/hw/misc/imx6_src.o
  CC      arm-softmmu/hw/misc/imx6_ccm.o
  CC      arm-softmmu/hw/misc/mst_fpga.o
  CC      arm-softmmu/hw/misc/omap_clk.o
  CC      x86_64-softmmu/hw/display/virtio-gpu-3d.o
  CC      x86_64-softmmu/hw/display/virtio-gpu-pci.o
  CC      arm-softmmu/hw/misc/omap_gpmc.o
  CC      arm-softmmu/hw/misc/omap_l4.o
  CC      arm-softmmu/hw/misc/omap_sdrc.o
  CC      x86_64-softmmu/hw/display/virtio-vga.o
  CC      arm-softmmu/hw/misc/omap_tap.o
  CC      x86_64-softmmu/hw/intc/apic.o
  CC      arm-softmmu/hw/misc/bcm2835_mbox.o
  CC      arm-softmmu/hw/misc/bcm2835_property.o
  CC      arm-softmmu/hw/misc/bcm2835_rng.o
  CC      x86_64-softmmu/hw/intc/apic_common.o
  CC      arm-softmmu/hw/misc/zynq_slcr.o
  CC      arm-softmmu/hw/misc/zynq-xadc.o
  CC      arm-softmmu/hw/misc/stm32f2xx_syscfg.o
  CC      arm-softmmu/hw/misc/edu.o
  CC      arm-softmmu/hw/misc/aspeed_scu.o
  CC      x86_64-softmmu/hw/intc/ioapic.o
  CC      arm-softmmu/hw/misc/aspeed_sdmc.o
  CC      arm-softmmu/hw/net/virtio-net.o
  CC      x86_64-softmmu/hw/isa/lpc_ich9.o
  CC      ppc-softmmu/target/ppc/mmu-hash32.o
  CC      arm-softmmu/hw/net/vhost_net.o
  CC      arm-softmmu/hw/pcmcia/pxa2xx.o
  CC      arm-softmmu/hw/scsi/virtio-scsi.o
  CC      arm-softmmu/hw/scsi/virtio-scsi-dataplane.o
  CC      x86_64-softmmu/hw/misc/vmport.o
  CC      ppc-softmmu/target/ppc/monitor.o
  CC      ppc-softmmu/target/ppc/arch_dump.o
  CC      arm-softmmu/hw/scsi/vhost-scsi.o
  CC      x86_64-softmmu/hw/misc/ivshmem.o
  CC      arm-softmmu/hw/sd/omap_mmc.o
  CC      x86_64-softmmu/hw/misc/pvpanic.o
  CC      ppc-softmmu/target/ppc/kvm-stub.o
  CC      ppc-softmmu/target/ppc/dfp_helper.o
  CC      arm-softmmu/hw/sd/pxa2xx_mmci.o
  CC      arm-softmmu/hw/sd/bcm2835_sdhost.o
  CC      ppc-softmmu/target/ppc/excp_helper.o
  CC      x86_64-softmmu/hw/misc/edu.o
  CC      arm-softmmu/hw/ssi/omap_spi.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_linux_arm.o
  CC      arm-softmmu/hw/ssi/imx_spi.o
  CC      arm-softmmu/hw/timer/exynos4210_mct.o
  CC      x86_64-softmmu/hw/misc/hyperv_testdev.o
  CC      arm-softmmu/hw/timer/exynos4210_pwm.o
  CC      x86_64-softmmu/hw/net/virtio-net.o
  CC      arm-softmmu/hw/timer/exynos4210_rtc.o
  CC      arm-softmmu/hw/timer/omap_gptimer.o
  CC      x86_64-softmmu/hw/net/vhost_net.o
  CC      arm-softmmu/hw/timer/omap_synctimer.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_linux_x86.o
  CC      x86_64-softmmu/hw/scsi/virtio-scsi.o
  CC      arm-softmmu/hw/timer/pxa2xx_timer.o
  CC      ppc-softmmu/target/ppc/fpu_helper.o
  CC      arm-softmmu/hw/timer/digic-timer.o
  CC      ppc-softmmu/target/ppc/int_helper.o
  CC      arm-softmmu/hw/timer/allwinner-a10-pit.o
  CC      arm-softmmu/hw/usb/tusb6010.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_xpsp2_x86.o
  CC      arm-softmmu/hw/vfio/common.o
  CC      arm-softmmu/hw/vfio/pci.o
  CC      arm-softmmu/hw/vfio/pci-quirks.o
  CC      arm-softmmu/hw/vfio/platform.o
  CC      x86_64-softmmu/hw/scsi/virtio-scsi-dataplane.o
  CC      x86_64-softmmu/hw/scsi/vhost-scsi.o
  CC      arm-softmmu/hw/vfio/calxeda-xgmac.o
  CC      arm-softmmu/hw/vfio/amd-xgbe.o
  CC      x86_64-softmmu/hw/timer/mc146818rtc.o
  CC      arm-softmmu/hw/vfio/spapr.o
  CC      arm-softmmu/hw/virtio/virtio.o
  CC      arm-softmmu/hw/virtio/virtio-balloon.o
  CC      arm-softmmu/hw/virtio/vhost.o
  CC      arm-softmmu/hw/virtio/vhost-backend.o
  CC      x86_64-softmmu/hw/vfio/common.o
  CC      arm-softmmu/hw/virtio/vhost-user.o
  CC      arm-softmmu/hw/virtio/vhost-vsock.o
  CC      arm-softmmu/hw/virtio/virtio-crypto.o
  CC      arm-softmmu/hw/virtio/virtio-crypto-pci.o
  CC      arm-softmmu/hw/arm/boot.o
  CC      arm-softmmu/hw/arm/collie.o
  CC      arm-softmmu/hw/arm/exynos4_boards.o
  CC      arm-softmmu/hw/arm/gumstix.o
  CC      x86_64-softmmu/hw/vfio/pci.o
  CC      arm-softmmu/hw/arm/highbank.o
  CC      arm-softmmu/hw/arm/digic_boards.o
  CC      arm-softmmu/hw/arm/integratorcp.o
  CC      arm-softmmu/hw/arm/mainstone.o
  CC      ppc-softmmu/target/ppc/timebase_helper.o
  CC      arm-softmmu/hw/arm/musicpal.o
  CC      arm-softmmu/hw/arm/nseries.o
  CC      arm-softmmu/hw/arm/omap_sx1.o
  CC      arm-softmmu/hw/arm/palm.o
  CC      ppc-softmmu/target/ppc/misc_helper.o
  CC      arm-softmmu/hw/arm/realview.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_linux_x86.o
  CC      arm-softmmu/hw/arm/spitz.o
  CC      arm-softmmu/hw/arm/stellaris.o
  CC      ppc-softmmu/target/ppc/mem_helper.o
  CC      arm-softmmu/hw/arm/tosa.o
  CC      arm-softmmu/hw/arm/versatilepb.o
  CC      arm-softmmu/hw/arm/vexpress.o
  CC      arm-softmmu/hw/arm/virt.o
  CC      arm-softmmu/hw/arm/xilinx_zynq.o
  CC      arm-softmmu/hw/arm/z2.o
  CC      arm-softmmu/hw/arm/virt-acpi-build.o
  CC      ppc-softmmu/target/ppc/gdbstub.o
  CC      x86_64-softmmu/hw/vfio/pci-quirks.o
  CC      arm-softmmu/hw/arm/netduino2.o
  CC      arm-softmmu/hw/arm/sysbus-fdt.o
  CC      arm-softmmu/hw/arm/armv7m.o
  CC      arm-softmmu/hw/arm/exynos4210.o
  GEN     trace/generated-helpers.c
  CC      arm-softmmu/hw/arm/pxa2xx.o
  CC      arm-softmmu/hw/arm/pxa2xx_gpio.o
  CC      ppc-softmmu/trace/control-target.o
  CC      arm-softmmu/hw/arm/pxa2xx_pic.o
  CC      arm-softmmu/hw/arm/digic.o
  CC      arm-softmmu/hw/arm/omap1.o
  CC      arm-softmmu/hw/arm/omap2.o
  CC      ppc-softmmu/panda/src/rr/rr_print.o
  CC      x86_64-softmmu/hw/vfio/platform.o
  CC      arm-softmmu/hw/arm/strongarm.o
  CC      arm-softmmu/hw/arm/allwinner-a10.o
  PROTO   ppc-softmmu/plog_pb2.py 
  CC      ppc-softmmu/panda/src/rr/rr_rmvapic.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_xpsp2_x86.o
  CC      x86_64-softmmu/hw/vfio/spapr.o
  CC      arm-softmmu/hw/arm/cubieboard.o
  CC      arm-softmmu/hw/arm/bcm2835_peripherals.o
  CXX     ppc-softmmu/panda/src/plog_reader.o
  CXX-gen i386-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_2000_x86.o
  CC      x86_64-softmmu/hw/virtio/virtio.o
  CC      arm-softmmu/hw/arm/bcm2836.o
  CC      arm-softmmu/hw/arm/raspi.o
  CC      arm-softmmu/hw/arm/stm32f205_soc.o
  CC      arm-softmmu/hw/arm/fsl-imx25.o
  CXX     ppc-softmmu/panda/plugins/asidstory/asidstory.o
  CC      arm-softmmu/hw/arm/imx25_pdk.o
  CC      arm-softmmu/hw/arm/fsl-imx31.o
  CC      arm-softmmu/hw/arm/kzm.o
  CC      arm-softmmu/hw/arm/fsl-imx6.o
  CC      arm-softmmu/hw/arm/sabrelite.o
  CC      arm-softmmu/hw/arm/aspeed_soc.o
  CC      arm-softmmu/hw/arm/aspeed.o
  CXX     ppc-softmmu/panda/plugins/callstack_instr/callstack_instr.o
  CC      arm-softmmu/target/arm/arm-semi.o
  CC      arm-softmmu/target/arm/machine.o
  CC      arm-softmmu/target/arm/psci.o
  CC      arm-softmmu/target/arm/arch_dump.o
  CC      x86_64-softmmu/hw/virtio/virtio-balloon.o
  CC      arm-softmmu/target/arm/monitor.o
  CC      arm-softmmu/target/arm/kvm-stub.o
  CC      arm-softmmu/target/arm/translate.o
  CC      arm-softmmu/target/arm/op_helper.o
  CC      arm-softmmu/target/arm/helper.o
  DSO     panda/plugins/syscalls2_dso_info_windows_xpsp3_x86.so
  DSO     panda/plugins/syscalls2_dso_info_linux_arm.so
  CC      arm-softmmu/target/arm/cpu.o
  DSO     panda/plugins/syscalls2_dso_info_windows_xpsp2_x86.so
  CC      x86_64-softmmu/hw/virtio/vhost.o
  DSO     panda/plugins/syscalls2_dso_info_linux_x86.so
  DSO     panda/plugins/syscalls2_dso_info_windows_2000_x86.so
  DSO     panda/plugins/syscalls2_dso_info_windows_7_x86.so
  CC      ppc-softmmu/panda/plugins/checkpoint/checkpoint.o
  CC      arm-softmmu/target/arm/neon_helper.o
  CC      x86_64-softmmu/hw/virtio/vhost-backend.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_checkpoint.so 
  CC      x86_64-softmmu/hw/virtio/vhost-user.o
  CXX     ppc-softmmu/panda/plugins/libfi/libfi.o
  CC      x86_64-softmmu/hw/virtio/vhost-vsock.o
  CC      x86_64-softmmu/hw/virtio/virtio-crypto.o
  CC      arm-softmmu/target/arm/iwmmxt_helper.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_callstack_instr.so 
  CC      x86_64-softmmu/hw/virtio/virtio-crypto-pci.o
  CXX     ppc-softmmu/panda/plugins/loaded/loaded.o
  CC      x86_64-softmmu/hw/xen/xen-host-pci-device.o
  CC      x86_64-softmmu/hw/xen/xen_pt.o
  CC      x86_64-softmmu/hw/xen/xen_pt_config_init.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_libfi.so 
  CC      arm-softmmu/target/arm/gdbstub.o
  CC      x86_64-softmmu/hw/xen/xen_pt_graphics.o
  CC      ppc-softmmu/panda/plugins/osi/os_intro.o
  CC      arm-softmmu/target/arm/crypto_helper.o
  CC      arm-softmmu/target/arm/arm-powerctl.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_loaded.so 
  CC      x86_64-softmmu/hw/xen/xen_pt_msi.o
  GEN     trace/generated-helpers.c
  PLUGIN  ppc-softmmu/panda/plugins/panda_osi.so 
  CC      arm-softmmu/trace/control-target.o
  CC      x86_64-softmmu/hw/i386/multiboot.o
  CC      arm-softmmu/panda/src/rr/rr_print.o
  CXX     ppc-softmmu/panda/plugins/osi_linux/osi_linux.o
  CC      ppc-softmmu/panda/plugins/osi_test/osi_test.o
  PROTO   arm-softmmu/plog_pb2.py 
  CC      arm-softmmu/panda/src/rr/rr_rmvapic.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_asidstory.so 
  CXX     arm-softmmu/panda/src/plog_reader.o
  CC      x86_64-softmmu/hw/i386/pc.o
  CC      x86_64-softmmu/hw/i386/pc_piix.o
  CC      ppc-softmmu/panda/plugins/wintrospection/wintrospection.o
  CXX     arm-softmmu/panda/plugins/asidstory/asidstory.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_osi_test.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_wintrospection.so 
  CXX     arm-softmmu/panda/plugins/callstack_instr/callstack_instr.o
  CXX     ppc-softmmu/panda/plugins/winxpx86intro/winxpx86intro.o
  CC      x86_64-softmmu/hw/i386/pc_q35.o
  PLUGIN  i386-softmmu/panda/plugins/panda_syscalls2.so 
  CC      x86_64-softmmu/hw/i386/pc_sysfw.o
  CC      x86_64-softmmu/hw/i386/x86-iommu.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_winxpx86intro.so 
  CXX     ppc-softmmu/panda/plugins/osi_linux/default_profile.o
  CC      x86_64-softmmu/hw/i386/intel_iommu.o
  UTIL CC ppc-softmmu/panda/plugins/osi_linux/kernelinfo_read.o 
  CXX     ppc-softmmu/panda/plugins/win7x86intro/win7x86intro.o
  CXX     ppc-softmmu/panda/plugins/win2000x86intro/win2000x86intro.o
  CC      x86_64-softmmu/hw/i386/amd_iommu.o
  CC      x86_64-softmmu/hw/i386/kvmvapic.o
  CXX     ppc-softmmu/panda/plugins/osi_linux/kernel_2_4_x_profile.o
  CC      x86_64-softmmu/hw/i386/acpi-build.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_win7x86intro.so 
  CP      ppc-softmmu/panda/plugins/osi_linux/kernelinfo.conf 
  CC      x86_64-softmmu/hw/i386/pci-assign-load-rom.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_win2000x86intro.so 
  CXX     ppc-softmmu/panda/plugins/syscalls2/syscalls2.o
  CC      arm-softmmu/panda/plugins/checkpoint/checkpoint.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_osi_linux.so 
  CC      ppc-softmmu/panda/plugins/syscalls2/syscalls2_info.o
  CC      x86_64-softmmu/hw/i386/kvm/clock.o
  CC      x86_64-softmmu/hw/i386/../xenpv/xen_machine_pv.o
  CC      ppc-softmmu/panda/plugins/pri/pri.o
  PLUGIN  arm-softmmu/panda/plugins/panda_checkpoint.so 
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_2000_x86.o
  CXX     arm-softmmu/panda/plugins/libfi/libfi.o
  CC      x86_64-softmmu/hw/i386/kvm/apic.o
  CC      x86_64-softmmu/hw/i386/kvm/i8259.o
  CC      x86_64-softmmu/hw/i386/kvm/ioapic.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_pri.so 
  CXX     ppc-softmmu/panda/plugins/pri_dwarf/pri_dwarf.o
  CC      x86_64-softmmu/hw/i386/kvm/i8254.o
  CC      x86_64-softmmu/hw/i386/kvm/pci-assign.o
  CC      x86_64-softmmu/hw/i386/xen/xen_platform.o
  PLUGIN  arm-softmmu/panda/plugins/panda_callstack_instr.so 
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_7_x86.o
  CC      x86_64-softmmu/hw/i386/xen/xen_apic.o
  CXX     arm-softmmu/panda/plugins/loaded/loaded.o
  CC      x86_64-softmmu/hw/i386/xen/xen_pvdevice.o
  CC      x86_64-softmmu/target/i386/translate.o
  CC      x86_64-softmmu/target/i386/helper.o
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_7_x86.o
  CC      x86_64-softmmu/target/i386/cpu.o
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_xpsp3_x86.o
  PLUGIN  arm-softmmu/panda/plugins/panda_libfi.so 
  CC      x86_64-softmmu/target/i386/bpt_helper.o
  CC      arm-softmmu/panda/plugins/osi/os_intro.o
  PLUGIN  arm-softmmu/panda/plugins/panda_loaded.so 
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_linux_arm.o
  CC      x86_64-softmmu/target/i386/excp_helper.o
  CC      x86_64-softmmu/target/i386/fpu_helper.o
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_xpsp3_x86.o
  CC      arm-softmmu/panda/plugins/osi_test/osi_test.o
  PLUGIN  arm-softmmu/panda/plugins/panda_osi.so 
  CC      x86_64-softmmu/target/i386/cc_helper.o
  CXX     arm-softmmu/panda/plugins/osi_linux/osi_linux.o
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_linux_arm.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_pri_dwarf.so 
  CC      x86_64-softmmu/target/i386/int_helper.o
  PLUGIN  arm-softmmu/panda/plugins/panda_osi_test.so 
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_linux_x86.o
  PLUGIN  arm-softmmu/panda/plugins/panda_asidstory.so 
  CC      arm-softmmu/panda/plugins/wintrospection/wintrospection.o
  CXX     ppc-softmmu/panda/plugins/pri_simple/pri_simple.o
  CC      ppc-softmmu/panda/plugins/scissors/scissors.o
  CXX     arm-softmmu/panda/plugins/winxpx86intro/winxpx86intro.o
  CC      x86_64-softmmu/target/i386/svm_helper.o
  PLUGIN  arm-softmmu/panda/plugins/panda_wintrospection.so 
  CC      x86_64-softmmu/target/i386/smm_helper.o
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_xpsp2_x86.o
  CXX     arm-softmmu/panda/plugins/win7x86intro/win7x86intro.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_pri_simple.so 
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_linux_x86.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_scissors.so 
  CXX     ppc-softmmu/panda/plugins/stringsearch/stringsearch.o
  CC      x86_64-softmmu/target/i386/misc_helper.o
  PLUGIN  arm-softmmu/panda/plugins/panda_winxpx86intro.so 
  CXX     ppc-softmmu/panda/plugins/asid_instr_count/asid_instr_count.o
  CXX     arm-softmmu/panda/plugins/win2000x86intro/win2000x86intro.o
  PLUGIN  arm-softmmu/panda/plugins/panda_win7x86intro.so 
  CC      x86_64-softmmu/target/i386/mem_helper.o
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_xpsp2_x86.o
  CXX     arm-softmmu/panda/plugins/syscalls2/syscalls2.o
  CXX-gen ppc-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_2000_x86.o
  CC      x86_64-softmmu/target/i386/seg_helper.o
  PLUGIN  arm-softmmu/panda/plugins/panda_win2000x86intro.so 
  CC      x86_64-softmmu/target/i386/mpx_helper.o
  CC      arm-softmmu/panda/plugins/pri/pri.o
  UTIL CC arm-softmmu/panda/plugins/osi_linux/kernelinfo_read.o 
  DSO     panda/plugins/syscalls2_dso_info_windows_xpsp3_x86.so
  CXX     arm-softmmu/panda/plugins/osi_linux/default_profile.o
  DSO     panda/plugins/syscalls2_dso_info_linux_arm.so
  DSO     panda/plugins/syscalls2_dso_info_windows_xpsp2_x86.so
  DSO     panda/plugins/syscalls2_dso_info_linux_x86.so
  DSO     panda/plugins/syscalls2_dso_info_windows_2000_x86.so
  PLUGIN  arm-softmmu/panda/plugins/panda_pri.so 
  DSO     panda/plugins/syscalls2_dso_info_windows_7_x86.so
  CC      x86_64-softmmu/target/i386/gdbstub.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_syscalls2.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_asid_instr_count.so 
  CXX     arm-softmmu/panda/plugins/pri_simple/pri_simple.o
  CXX     arm-softmmu/panda/plugins/pri_dwarf/pri_dwarf.o
  CC      x86_64-softmmu/target/i386/machine.o
  CXX     arm-softmmu/panda/plugins/osi_linux/kernel_2_4_x_profile.o
  CC      ppc-softmmu/panda/plugins/replaymovie/replaymovie.o
  CC      ppc-softmmu/panda/plugins/memsavep/memsavep.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_stringsearch.so 
  PLUGIN  arm-softmmu/panda/plugins/panda_pri_simple.so 
  CC      arm-softmmu/panda/plugins/scissors/scissors.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_replaymovie.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_memsavep.so 
  CXX     arm-softmmu/panda/plugins/stringsearch/stringsearch.o
  CXX     ppc-softmmu/panda/plugins/unigrams/unigrams.o
  CXX     ppc-softmmu/panda/plugins/textprinter/textprinter.o
  CXX     ppc-softmmu/panda/plugins/net/net.o
  CC      x86_64-softmmu/target/i386/arch_memory_mapping.o
  CP      arm-softmmu/panda/plugins/osi_linux/kernelinfo.conf 
  PLUGIN  arm-softmmu/panda/plugins/panda_osi_linux.so 
  PLUGIN  arm-softmmu/panda/plugins/panda_scissors.so 
  CXX     arm-softmmu/panda/plugins/asid_instr_count/asid_instr_count.o
  CC      x86_64-softmmu/target/i386/arch_dump.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_net.so 
  CC      arm-softmmu/panda/plugins/replaymovie/replaymovie.o
  CXX     ppc-softmmu/panda/plugins/network/network.o
  CC      x86_64-softmmu/target/i386/monitor.o
  PLUGIN  arm-softmmu/panda/plugins/panda_replaymovie.so 
  CC      arm-softmmu/panda/plugins/memsavep/memsavep.o
  CC      x86_64-softmmu/target/i386/kvm.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_unigrams.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_textprinter.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_network.so 
  PLUGIN  arm-softmmu/panda/plugins/panda_memsavep.so 
  CXX     ppc-softmmu/panda/plugins/filereadmon/filereadmon.o
  CXX     ppc-softmmu/panda/plugins/callfunc/callfunc.o
  CC      x86_64-softmmu/target/i386/hyperv.o
  CXX     ppc-softmmu/panda/plugins/mmio_trace/mmio_trace.o
  CXX     arm-softmmu/panda/plugins/unigrams/unigrams.o
  PLUGIN  arm-softmmu/panda/plugins/panda_pri_dwarf.so 
  GEN     trace/generated-helpers.c
  CC      x86_64-softmmu/trace/control-target.o
  PLUGIN  arm-softmmu/panda/plugins/panda_stringsearch.so 
  PLUGIN  arm-softmmu/panda/plugins/panda_asid_instr_count.so 
  CXX     arm-softmmu/panda/plugins/textprinter/textprinter.o
  CXX     arm-softmmu/panda/plugins/net/net.o
  CXX     arm-softmmu/panda/plugins/network/network.o
  CC      x86_64-softmmu/panda/src/rr/rr_print.o
  PLUGIN  arm-softmmu/panda/plugins/panda_net.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_mmio_trace.so 
  PLUGIN  arm-softmmu/panda/plugins/panda_network.so 
  PROTO   x86_64-softmmu/plog_pb2.py 
  CC      x86_64-softmmu/panda/src/rr/rr_rmvapic.o
  CXX     arm-softmmu/panda/plugins/filereadmon/filereadmon.o
  PLUGIN  arm-softmmu/panda/plugins/panda_unigrams.so 
  CXX     arm-softmmu/panda/plugins/callfunc/callfunc.o
  CXX     ppc-softmmu/panda/plugins/file_taint/file_taint.o
  CXX     arm-softmmu/panda/plugins/mmio_trace/mmio_trace.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_filereadmon.so 
  CXX     x86_64-softmmu/panda/src/plog_reader.o
  PLUGIN  arm-softmmu/panda/plugins/panda_textprinter.so 
  CXX     ppc-softmmu/panda/plugins/pri_trace/pri_trace.o
  CXX     ppc-softmmu/panda/plugins/pri_taint/pri_taint.o
  CXX     arm-softmmu/panda/plugins/file_taint/file_taint.o
  CXX     x86_64-softmmu/panda/plugins/asidstory/asidstory.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_callfunc.so 
  CXX     ppc-softmmu/panda/plugins/taint2/label_set.o
  PLUGIN  arm-softmmu/panda/plugins/panda_mmio_trace.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_file_taint.so 
  PLUGIN  arm-softmmu/panda/plugins/panda_filereadmon.so 
  CXX     arm-softmmu/panda/plugins/pri_taint/pri_taint.o
  CXX     x86_64-softmmu/panda/plugins/callstack_instr/callstack_instr.o
  CXX     ppc-softmmu/panda/plugins/tainted_branch/tainted_branch.o
  CXX     arm-softmmu/panda/plugins/pri_trace/pri_trace.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_pri_trace.so 
  CXX     ppc-softmmu/panda/plugins/tstringsearch/tstringsearch.o
  PLUGIN  arm-softmmu/panda/plugins/panda_callfunc.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_pri_taint.so 
  PLUGIN  arm-softmmu/panda/plugins/panda_file_taint.so 
  CXX     ppc-softmmu/panda/plugins/taint2/shad_dir_32.o
  CXX     arm-softmmu/panda/plugins/taint2/label_set.o
  CXX     ppc-softmmu/panda/plugins/tainted_instr/tainted_instr.o
  CXX     ppc-softmmu/panda/plugins/taint2/taint_ops.o
  CXX     arm-softmmu/panda/plugins/tainted_branch/tainted_branch.o
  PLUGIN  arm-softmmu/panda/plugins/panda_pri_taint.so 
  PLUGIN  arm-softmmu/panda/plugins/panda_pri_trace.so 
  CXX     arm-softmmu/panda/plugins/tstringsearch/tstringsearch.o
  CXX     arm-softmmu/panda/plugins/tainted_instr/tainted_instr.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_tstringsearch.so 
  CXX     arm-softmmu/panda/plugins/taint2/shad_dir_32.o
  CXX     ppc-softmmu/panda/plugins/ida_taint2/ida_taint2.o
  CXX     arm-softmmu/panda/plugins/taint2/taint_ops.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_tainted_branch.so 
  CXX     ppc-softmmu/panda/plugins/tainted_net/tainted_net.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_tainted_instr.so 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_callstack_instr.so 
  CXX     ppc-softmmu/panda/plugins/serial_taint/serial_taint.o
  CC      x86_64-softmmu/panda/plugins/checkpoint/checkpoint.o
  PLUGIN  arm-softmmu/panda/plugins/panda_tainted_branch.so 
  CC      arm-softmmu/panda/plugins/syscalls2/syscalls2_info.o
  CXX     x86_64-softmmu/panda/plugins/libfi/libfi.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_checkpoint.so 
  PLUGIN  arm-softmmu/panda/plugins/panda_tstringsearch.so 
  CXX     x86_64-softmmu/panda/plugins/loaded/loaded.o
  CXX     arm-softmmu/panda/plugins/ida_taint2/ida_taint2.o
  CXX     arm-softmmu/panda/plugins/tainted_net/tainted_net.o
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_2000_x86.o
  CXX     ppc-softmmu/panda/plugins/taint2/taint2.o
  PLUGIN  arm-softmmu/panda/plugins/panda_tainted_instr.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_ida_taint2.so 
  CXX     arm-softmmu/panda/plugins/serial_taint/serial_taint.o
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_7_x86.o
  PLUGIN  ppc-softmmu/panda/plugins/panda_tainted_net.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_serial_taint.so 
  CLANG   ppc-softmmu/fpu/softfloat.bc2 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_asidstory.so 
  CLANG   ppc-softmmu/target/ppc/excp_helper.bc2 
  CLANG   ppc-softmmu/target/ppc/fpu_helper.bc2 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_loaded.so 
  CC      x86_64-softmmu/panda/plugins/osi/os_intro.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_libfi.so 
  CC      x86_64-softmmu/panda/plugins/osi_test/osi_test.o
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_7_x86.o
  CLANG   ppc-softmmu/target/ppc/timebase_helper.bc2 
  CXX     x86_64-softmmu/panda/plugins/osi_linux/osi_linux.o
  CLANG   ppc-softmmu/target/ppc/misc_helper.bc2 
  PLUGIN  arm-softmmu/panda/plugins/panda_tainted_net.so 
  CLANG   ppc-softmmu/target/ppc/mmu_helper.bc2 
  UTIL CC x86_64-softmmu/panda/plugins/osi_linux/kernelinfo_read.o 
  CXX     x86_64-softmmu/panda/plugins/osi_linux/default_profile.o
  CXX     arm-softmmu/panda/plugins/taint2/taint2.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_osi.so 
  CXX     arm-softmmu/panda/plugins/taint2/shad_dir_64.o
  CLANG   arm-softmmu/fpu/softfloat.bc2 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_osi_test.so 
  CLANG   arm-softmmu/target/arm/op_helper.bc2 
  CLANG   arm-softmmu/target/arm/helper.bc2 
  CXX     x86_64-softmmu/panda/plugins/osi_linux/kernel_2_4_x_profile.o
  PLUGIN  arm-softmmu/panda/plugins/panda_serial_taint.so 
  PLUGIN  arm-softmmu/panda/plugins/panda_ida_taint2.so 
  CLANG   arm-softmmu/target/arm/neon_helper.bc2 
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_xpsp3_x86.o
  CXX     arm-softmmu/panda/plugins/taint2/taint_api.o
  CLANG   arm-softmmu/target/arm/iwmmxt_helper.bc2 
  CLANG   arm-softmmu/target/arm/crypto_helper.bc2 
  CC      arm-softmmu/gdbstub-xml.o
  CP      x86_64-softmmu/panda/plugins/osi_linux/kernelinfo.conf 
  LINK    arm-softmmu/rr_print_arm
  LINK    arm-softmmu/rr_rmvapic_arm
  PLUGIN  x86_64-softmmu/panda/plugins/panda_osi_linux.so 
  LINK    arm-softmmu/plog_reader
  CXX     arm-softmmu/panda/tools/helper_call_modifier.o
  CC      arm-softmmu/trace/generated-helpers.o
  CXX     ppc-softmmu/panda/plugins/taint2/shad_dir_64.o
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_linux_arm.o
  CC      x86_64-softmmu/panda/plugins/wintrospection/wintrospection.o
  CXX     x86_64-softmmu/panda/plugins/winxpx86intro/winxpx86intro.o
  CXX     x86_64-softmmu/panda/plugins/win7x86intro/win7x86intro.o
  CXX     ppc-softmmu/panda/plugins/taint2/taint_api.o
  LINK    arm-softmmu/qemu-system-arm
  CXX     x86_64-softmmu/panda/plugins/win2000x86intro/win2000x86intro.o
  CXX     ppc-softmmu/panda/plugins/taint2/shad.o
  LLVMLD  arm-softmmu/llvm-helpers.bc1 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_winxpx86intro.so 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_win7x86intro.so 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_win2000x86intro.so 
  CXX     x86_64-softmmu/panda/plugins/syscalls2/syscalls2.o
  CXX     ppc-softmmu/panda/plugins/taint2/llvm_taint_lib.o
  CXX     x86_64-softmmu/panda/plugins/pri_dwarf/pri_dwarf.o
  CC      x86_64-softmmu/panda/plugins/pri/pri.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_wintrospection.so 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_pri.so 
  CXX     arm-softmmu/panda/plugins/taint2/shad.o
  CC      x86_64-softmmu/panda/plugins/scissors/scissors.o
  CXX     x86_64-softmmu/panda/plugins/pri_simple/pri_simple.o
  CXX     ppc-softmmu/panda/plugins/taint2/taint2_hypercalls.o
  CXX     arm-softmmu/panda/plugins/taint2/llvm_taint_lib.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_pri_simple.so 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_scissors.so 
  CLANGXX ppc-softmmu/panda/plugins/taint2/taint_ops_llvm.bc 
  CXX     x86_64-softmmu/panda/plugins/stringsearch/stringsearch.o
  CXX     x86_64-softmmu/panda/plugins/asid_instr_count/asid_instr_count.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_pri_dwarf.so 
  CXX     arm-softmmu/panda/plugins/taint2/taint2_hypercalls.o
  CC      x86_64-softmmu/panda/plugins/replaymovie/replaymovie.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_replaymovie.so 
  LLVMLD  ppc-softmmu/panda/plugins/panda_taint2_ops.bc 
  CC      x86_64-softmmu/panda/plugins/syscalls2/syscalls2_info.o
  CC      x86_64-softmmu/panda/plugins/memsavep/memsavep.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_asid_instr_count.so 
  CXX     x86_64-softmmu/panda/plugins/unigrams/unigrams.o
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_2000_x86.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_memsavep.so 
  CXX     x86_64-softmmu/panda/plugins/textprinter/textprinter.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_stringsearch.so 
  CXX     x86_64-softmmu/panda/plugins/net/net.o
  CXX     x86_64-softmmu/panda/plugins/network/network.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_net.so 
  CXX     x86_64-softmmu/panda/plugins/filereadmon/filereadmon.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_network.so 
  CLANGXX arm-softmmu/panda/plugins/taint2/taint_ops_llvm.bc 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_unigrams.so 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_textprinter.so 
  CXX     x86_64-softmmu/panda/plugins/callfunc/callfunc.o
  CXX     x86_64-softmmu/panda/plugins/mmio_trace/mmio_trace.o
  CXX     x86_64-softmmu/panda/plugins/file_taint/file_taint.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_mmio_trace.so 
  CXX     x86_64-softmmu/panda/plugins/pri_taint/pri_taint.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_filereadmon.so 
  LLVMLD  arm-softmmu/panda/plugins/panda_taint2_ops.bc 
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_xpsp3_x86.o
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_linux_arm.o
  CXX     x86_64-softmmu/panda/plugins/pri_trace/pri_trace.o
  CXX     x86_64-softmmu/panda/plugins/taint2/label_set.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_file_taint.so 
  PLUGIN  ppc-softmmu/panda/plugins/panda_taint2.so 
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_linux_x86.o
  CXX     x86_64-softmmu/panda/plugins/tainted_branch/tainted_branch.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_callfunc.so 
  CXX     x86_64-softmmu/panda/plugins/tstringsearch/tstringsearch.o
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_xpsp2_x86.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_pri_trace.so 
  CXX     x86_64-softmmu/panda/plugins/taint2/shad_dir_32.o
  CXX     x86_64-softmmu/panda/plugins/tainted_instr/tainted_instr.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_pri_taint.so 
  CLANG   ppc-softmmu/target/ppc/mem_helper.bc2 
  CXX     x86_64-softmmu/panda/plugins/taint2/taint_ops.o
  PLUGIN  arm-softmmu/panda/plugins/panda_taint2.so 
  CXX     x86_64-softmmu/panda/plugins/ida_taint2/ida_taint2.o
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_linux_x86.o
  CLANG   ppc-softmmu/target/ppc/int_helper.bc2 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_tstringsearch.so 
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_xpsp2_x86.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_tainted_branch.so 
  CXX     x86_64-softmmu/panda/plugins/tainted_net/tainted_net.o
  CC      ppc-softmmu/gdbstub-xml.o
  LINK    ppc-softmmu/rr_print_ppc
  LINK    ppc-softmmu/rr_rmvapic_ppc
  CXX     x86_64-softmmu/panda/plugins/serial_taint/serial_taint.o
  CXX-gen arm-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_2000_x86.o
  LINK    ppc-softmmu/plog_reader
  LLVMLD  ppc-softmmu/llvm-helpers.bc1 
  DSO     panda/plugins/syscalls2_dso_info_windows_xpsp3_x86.so
  DSO     panda/plugins/syscalls2_dso_info_linux_arm.so
  CXX     ppc-softmmu/panda/tools/helper_call_modifier.o
  DSO     panda/plugins/syscalls2_dso_info_windows_xpsp2_x86.so
  CC      ppc-softmmu/trace/generated-helpers.o
  DSO     panda/plugins/syscalls2_dso_info_linux_x86.so
  PLUGIN  x86_64-softmmu/panda/plugins/panda_tainted_instr.so 
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_7_x86.o
  PLUGIN  x86_64-softmmu/panda/plugins/panda_ida_taint2.so 
  DSO     panda/plugins/syscalls2_dso_info_windows_2000_x86.so
  DSO     panda/plugins/syscalls2_dso_info_windows_7_x86.so
  CXX     x86_64-softmmu/panda/plugins/taint2/taint2.o
  CLANG   x86_64-softmmu/fpu/softfloat.bc2 
  CXX     x86_64-softmmu/panda/plugins/taint2/shad_dir_64.o
  CLANG   x86_64-softmmu/target/i386/helper.bc2 
  CLANG   x86_64-softmmu/target/i386/bpt_helper.bc2 
  CLANG   x86_64-softmmu/target/i386/excp_helper.bc2 
  LINK    ppc-softmmu/qemu-system-ppc
  CLANG   x86_64-softmmu/target/i386/fpu_helper.bc2 
  CLANG   x86_64-softmmu/target/i386/cc_helper.bc2 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_tainted_net.so 
  CLANG   x86_64-softmmu/target/i386/int_helper.bc2 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_serial_taint.so 
  CLANG   x86_64-softmmu/target/i386/svm_helper.bc2 
  CXX     x86_64-softmmu/panda/plugins/taint2/taint_api.o
  CLANG   x86_64-softmmu/target/i386/smm_helper.bc2 
  CLANG   x86_64-softmmu/target/i386/misc_helper.bc2 
  CLANG   x86_64-softmmu/target/i386/mem_helper.bc2 
  CLANG   x86_64-softmmu/target/i386/seg_helper.bc2 
  CLANG   x86_64-softmmu/target/i386/mpx_helper.bc2 
  CC      x86_64-softmmu/gdbstub-xml.o
  LINK    x86_64-softmmu/rr_print_x86_64
  LINK    x86_64-softmmu/rr_rmvapic_x86_64
  LINK    x86_64-softmmu/plog_reader
  CXX     x86_64-softmmu/panda/tools/helper_call_modifier.o
  CC      x86_64-softmmu/trace/generated-helpers.o
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_7_x86.o
  CXX     x86_64-softmmu/panda/plugins/taint2/shad.o
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_xpsp3_x86.o
  LINK    x86_64-softmmu/qemu-system-x86_64
  CXX     x86_64-softmmu/panda/plugins/taint2/llvm_taint_lib.o
  CXX     x86_64-softmmu/panda/plugins/taint2/taint2_hypercalls.o
  CLANGXX x86_64-softmmu/panda/plugins/taint2/taint_ops_llvm.bc 
  PLUGIN  arm-softmmu/panda/plugins/panda_syscalls2.so 
  LLVMLD  x86_64-softmmu/panda/plugins/panda_taint2_ops.bc 
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_linux_arm.o
  LINK    arm-softmmu/panda/tools/helper_call_modifier
  LLVMLD  x86_64-softmmu/llvm-helpers.bc1 
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_xpsp3_x86.o
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_linux_arm.o
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_linux_x86.o
  LLMORPH arm-softmmu/llvm-helpers.bc 
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_xpsp2_x86.o
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_linux_x86.o
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_enter_windows_xpsp2_x86.o
  CXX-gen x86_64-softmmu/panda/plugins/syscalls2/gen_syscall_switch_return_windows_2000_x86.o
  DSO     panda/plugins/syscalls2_dso_info_windows_xpsp3_x86.so
  DSO     panda/plugins/syscalls2_dso_info_linux_arm.so
  DSO     panda/plugins/syscalls2_dso_info_windows_xpsp2_x86.so
  DSO     panda/plugins/syscalls2_dso_info_windows_2000_x86.so
  DSO     panda/plugins/syscalls2_dso_info_linux_x86.so
  DSO     panda/plugins/syscalls2_dso_info_windows_7_x86.so
  LINK    ppc-softmmu/panda/tools/helper_call_modifier
  LLMORPH ppc-softmmu/llvm-helpers.bc 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_taint2.so 
  LINK    x86_64-softmmu/panda/tools/helper_call_modifier
  LLMORPH x86_64-softmmu/llvm-helpers.bc 
  PLUGIN  x86_64-softmmu/panda/plugins/panda_syscalls2.so 
wanghuozhu@dlserver:~/ws/other/panda$ 
```

```
wanghuozhu@dlserver:~/ws/other/panda/x86_64-softmmu$ qemu-system-x86_64 -h
QEMU emulator version 3.1.50 (v3.1.0-456-g9b2e891-dirty)
Copyright (c) 2003-2018 Fabrice Bellard and the QEMU Project developers
usage: qemu-system-x86_64 [options] [disk_image]

'disk_image' is a raw hard disk image for IDE hard disk 0

Standard options:
-h or -help     display this help and exit
-version        display version information and exit
-machine [type=]name[,prop[=value][,...]]
                selects emulated machine ('-machine help' for list)
                property accel=accel1[:accel2[:...]] selects accelerator
                supported accelerators are kvm, xen, hax, hvf, whpx or tcg (default: tcg)
                kernel_irqchip=on|off|split controls accelerated irqchip support (default=off)
                vmport=on|off|auto controls emulation of vmport (default: auto)
                kvm_shadow_mem=size of KVM shadow MMU in bytes
                dump-guest-core=on|off include guest memory in a core dump (default=on)
                mem-merge=on|off controls memory merge support (default: on)
                igd-passthru=on|off controls IGD GFX passthrough support (default=off)
                aes-key-wrap=on|off controls support for AES key wrapping (default=on)
                dea-key-wrap=on|off controls support for DEA key wrapping (default=on)
                suppress-vmdesc=on|off disables self-describing migration (default=off)
                nvdimm=on|off controls NVDIMM support (default=off)
                enforce-config-section=on|off enforce configuration section migration (default=off)
                memory-encryption=@var{} memory encryption object to use (default=none)
-cpu cpu        select CPU ('-cpu help' for list)
-accel [accel=]accelerator[,thread=single|multi]
                select accelerator (kvm, xen, hax, hvf, whpx or tcg; use 'help' for a list)
                thread=single|multi (enable multi-threaded TCG)
-smp [cpus=]n[,maxcpus=cpus][,cores=cores][,threads=threads][,sockets=sockets]
                set the number of CPUs to 'n' [default=1]
                maxcpus= maximum number of total cpus, including
                offline CPUs for hotplug, etc
                cores= number of CPU cores on one socket
                threads= number of threads on one CPU core
                sockets= number of discrete sockets in the system
-numa node[,mem=size][,cpus=firstcpu[-lastcpu]][,nodeid=node]
-numa node[,memdev=id][,cpus=firstcpu[-lastcpu]][,nodeid=node]
-numa dist,src=source,dst=destination,val=distance
-numa cpu,node-id=node[,socket-id=x][,core-id=y][,thread-id=z]
-add-fd fd=fd,set=set[,opaque=opaque]
                Add 'fd' to fd 'set'
-set group.id.arg=value
                set <arg> parameter for item <id> of type <group>
                i.e. -set drive.$id.file=/path/to/image
-global driver.property=value
-global driver=driver,property=property,value=value
                set a global default for a driver property
-boot [order=drives][,once=drives][,menu=on|off]
      [,splash=sp_name][,splash-time=sp_time][,reboot-timeout=rb_time][,strict=on|off]
                'drives': floppy (a), hard disk (c), CD-ROM (d), network (n)
                'sp_name': the file's name that would be passed to bios as logo picture, if menu=on
                'sp_time': the period that splash picture last if menu=on, unit is ms
                'rb_timeout': the timeout before guest reboot when boot failed, unit is ms
-m [size=]megs[,slots=n,maxmem=size]
                configure guest RAM
                size: initial amount of guest memory
                slots: number of hotplug slots (default: none)
                maxmem: maximum amount of guest memory (default: none)
NOTE: Some architectures might enforce a specific granularity
-mem-path FILE  provide backing storage for guest RAM
-mem-prealloc   preallocate guest memory (use with -mem-path)
-k language     use keyboard layout (for example 'fr' for French)
-audio-help     print list of audio drivers and their options
-soundhw c1,... enable audio support
                and only specified sound cards (comma separated list)
                use '-soundhw help' to get the list of supported cards
                use '-soundhw all' to enable all of them
-device driver[,prop[=value][,...]]
                add device (based on driver)
                prop=value,... sets driver properties
                use '-device help' to print all possible drivers
                use '-device driver,help' to print all possible properties
-name string1[,process=string2][,debug-threads=on|off]
                set the name of the guest
                string1 sets the window title and string2 the process name (on Linux)
                When debug-threads is enabled, individual threads are given a separate name (on Linux)
                NOTE: The thread names are for debugging and not a stable API.
-uuid %08x-%04x-%04x-%04x-%012x
                specify machine UUID

Block device options:
-fda/-fdb file  use 'file' as floppy disk 0/1 image
-hda/-hdb file  use 'file' as IDE hard disk 0/1 image
-hdc/-hdd file  use 'file' as IDE hard disk 2/3 image
-cdrom file     use 'file' as IDE cdrom image (cdrom is ide1 master)
-blockdev [driver=]driver[,node-name=N][,discard=ignore|unmap]
          [,cache.direct=on|off][,cache.no-flush=on|off]
          [,read-only=on|off][,detect-zeroes=on|off|unmap]
          [,driver specific parameters...]
                configure a block backend
-drive [file=file][,if=type][,bus=n][,unit=m][,media=d][,index=i]
       [,cache=writethrough|writeback|none|directsync|unsafe][,format=f]
       [,snapshot=on|off][,rerror=ignore|stop|report]
       [,werror=ignore|stop|report|enospc][,id=name][,aio=threads|native]
       [,readonly=on|off][,copy-on-read=on|off]
       [,discard=ignore|unmap][,detect-zeroes=on|off|unmap]
       [[,bps=b]|[[,bps_rd=r][,bps_wr=w]]]
       [[,iops=i]|[[,iops_rd=r][,iops_wr=w]]]
       [[,bps_max=bm]|[[,bps_rd_max=rm][,bps_wr_max=wm]]]
       [[,iops_max=im]|[[,iops_rd_max=irm][,iops_wr_max=iwm]]]
       [[,iops_size=is]]
       [[,group=g]]
                use 'file' as a drive image
-mtdblock file  use 'file' as on-board Flash memory image
-sd file        use 'file' as SecureDigital card image
-pflash file    use 'file' as a parallel flash image
-snapshot       write to temporary files instead of disk image files
-fsdev fsdriver,id=id[,path=path,][security_model={mapped-xattr|mapped-file|passthrough|none}]
 [,writeout=immediate][,readonly][,socket=socket|sock_fd=sock_fd][,fmode=fmode][,dmode=dmode]
 [[,throttling.bps-total=b]|[[,throttling.bps-read=r][,throttling.bps-write=w]]]
 [[,throttling.iops-total=i]|[[,throttling.iops-read=r][,throttling.iops-write=w]]]
 [[,throttling.bps-total-max=bm]|[[,throttling.bps-read-max=rm][,throttling.bps-write-max=wm]]]
 [[,throttling.iops-total-max=im]|[[,throttling.iops-read-max=irm][,throttling.iops-write-max=iwm]]]
 [[,throttling.iops-size=is]]
-virtfs local,path=path,mount_tag=tag,security_model=[mapped-xattr|mapped-file|passthrough|none]
        [,id=id][,writeout=immediate][,readonly][,socket=socket|sock_fd=sock_fd][,fmode=fmode][,dmode=dmode]
-virtfs_synth Create synthetic file system image
-iscsi [user=user][,password=password]
       [,header-digest=CRC32C|CR32C-NONE|NONE-CRC32C|NONE
       [,initiator-name=initiator-iqn][,id=target-iqn]
       [,timeout=timeout]
                iSCSI session parameters

USB options:
-usb            enable the USB driver (if it is not used by default yet)
-usbdevice name add the host or guest USB device 'name'

Display options:
-display sdl[,frame=on|off][,alt_grab=on|off][,ctrl_grab=on|off]
            [,window_close=on|off][,gl=on|core|es|off]
-display gtk[,grab_on_hover=on|off][,gl=on|off]|
-display vnc=<display>[,<optargs>]
-display curses
-display none
-display egl-headless[,rendernode=<file>]                select display type
The default display is equivalent to
	"-display sdl"
-nographic      disable graphical output and redirect serial I/Os to console
-curses         shorthand for -display curses
-no-frame       open SDL window without a frame and window decorations
-alt-grab       use Ctrl-Alt-Shift to grab mouse (instead of Ctrl-Alt)
-ctrl-grab      use Right-Ctrl to grab mouse (instead of Ctrl-Alt)
-no-quit        disable SDL window close capability
-sdl            shorthand for -display sdl
-spice [port=port][,tls-port=secured-port][,x509-dir=<dir>]
       [,x509-key-file=<file>][,x509-key-password=<file>]
       [,x509-cert-file=<file>][,x509-cacert-file=<file>]
       [,x509-dh-key-file=<file>][,addr=addr][,ipv4|ipv6|unix]
       [,tls-ciphers=<list>]
       [,tls-channel=[main|display|cursor|inputs|record|playback]]
       [,plaintext-channel=[main|display|cursor|inputs|record|playback]]
       [,sasl][,password=<secret>][,disable-ticketing]
       [,image-compression=[auto_glz|auto_lz|quic|glz|lz|off]]
       [,jpeg-wan-compression=[auto|never|always]]
       [,zlib-glz-wan-compression=[auto|never|always]]
       [,streaming-video=[off|all|filter]][,disable-copy-paste]
       [,disable-agent-file-xfer][,agent-mouse=[on|off]]
       [,playback-compression=[on|off]][,seamless-migration=[on|off]]
       [,gl=[on|off]][,rendernode=<file>]
   enable spice
   at least one of {port, tls-port} is mandatory
-portrait       rotate graphical output 90 deg left (only PXA LCD)
-rotate <deg>   rotate graphical output some deg left (only PXA LCD)
-vga [std|cirrus|vmware|qxl|xenfb|tcx|cg3|virtio|none]
                select video card type
-full-screen    start in full screen
-vnc <display>  shorthand for -display vnc=<display>

i386 target only:
-win2k-hack     use it when installing Windows 2000 to avoid a disk full bug
-no-fd-bootchk  disable boot signature checking for floppy disks
-no-acpi        disable ACPI
-no-hpet        disable HPET
-acpitable [sig=str][,rev=n][,oem_id=str][,oem_table_id=str][,oem_rev=n][,asl_compiler_id=str][,asl_compiler_rev=n][,{data|file}=file1[:file2]...]
                ACPI table description
-smbios file=binary
                load SMBIOS entry from binary file
-smbios type=0[,vendor=str][,version=str][,date=str][,release=%d.%d]
              [,uefi=on|off]
                specify SMBIOS type 0 fields
-smbios type=1[,manufacturer=str][,product=str][,version=str][,serial=str]
              [,uuid=uuid][,sku=str][,family=str]
                specify SMBIOS type 1 fields
-smbios type=2[,manufacturer=str][,product=str][,version=str][,serial=str]
              [,asset=str][,location=str]
                specify SMBIOS type 2 fields
-smbios type=3[,manufacturer=str][,version=str][,serial=str][,asset=str]
              [,sku=str]
                specify SMBIOS type 3 fields
-smbios type=4[,sock_pfx=str][,manufacturer=str][,version=str][,serial=str]
              [,asset=str][,part=str]
                specify SMBIOS type 4 fields
-smbios type=17[,loc_pfx=str][,bank=str][,manufacturer=str][,serial=str]
               [,asset=str][,part=str][,speed=%d]
                specify SMBIOS type 17 fields

Network options:
-netdev user,id=str[,ipv4[=on|off]][,net=addr[/mask]][,host=addr]
         [,ipv6[=on|off]][,ipv6-net=addr[/int]][,ipv6-host=addr]
         [,restrict=on|off][,hostname=host][,dhcpstart=addr]
         [,dns=addr][,ipv6-dns=addr][,dnssearch=domain][,domainname=domain]
         [,tftp=dir][,tftp-server-name=name][,bootfile=f][,hostfwd=rule][,guestfwd=rule][,smb=dir[,smbserver=addr]]
                configure a user mode network backend with ID 'str',
                its DHCP server and optional services
-netdev tap,id=str[,fd=h][,fds=x:y:...:z][,ifname=name][,script=file][,downscript=dfile]
         [,br=bridge][,helper=helper][,sndbuf=nbytes][,vnet_hdr=on|off][,vhost=on|off]
         [,vhostfd=h][,vhostfds=x:y:...:z][,vhostforce=on|off][,queues=n]
         [,poll-us=n]
                configure a host TAP network backend with ID 'str'
                connected to a bridge (default=br0)
                use network scripts 'file' (default=/etc/qemu-ifup)
                to configure it and 'dfile' (default=/etc/qemu-ifdown)
                to deconfigure it
                use '[down]script=no' to disable script execution
                use network helper 'helper' (default=/usr/local/libexec/qemu-bridge-helper) to
                configure it
                use 'fd=h' to connect to an already opened TAP interface
                use 'fds=x:y:...:z' to connect to already opened multiqueue capable TAP interfaces
                use 'sndbuf=nbytes' to limit the size of the send buffer (the
                default is disabled 'sndbuf=0' to enable flow control set 'sndbuf=1048576')
                use vnet_hdr=off to avoid enabling the IFF_VNET_HDR tap flag
                use vnet_hdr=on to make the lack of IFF_VNET_HDR support an error condition
                use vhost=on to enable experimental in kernel accelerator
                    (only has effect for virtio guests which use MSIX)
                use vhostforce=on to force vhost on for non-MSIX virtio guests
                use 'vhostfd=h' to connect to an already opened vhost net device
                use 'vhostfds=x:y:...:z to connect to multiple already opened vhost net devices
                use 'queues=n' to specify the number of queues to be created for multiqueue TAP
                use 'poll-us=n' to speciy the maximum number of microseconds that could be
                spent on busy polling for vhost net
-netdev bridge,id=str[,br=bridge][,helper=helper]
                configure a host TAP network backend with ID 'str' that is
                connected to a bridge (default=br0)
                using the program 'helper (default=/usr/local/libexec/qemu-bridge-helper)
-netdev l2tpv3,id=str,src=srcaddr,dst=dstaddr[,srcport=srcport][,dstport=dstport]
         [,rxsession=rxsession],txsession=txsession[,ipv6=on/off][,udp=on/off]
         [,cookie64=on/off][,counter][,pincounter][,txcookie=txcookie]
         [,rxcookie=rxcookie][,offset=offset]
                configure a network backend with ID 'str' connected to
                an Ethernet over L2TPv3 pseudowire.
                Linux kernel 3.3+ as well as most routers can talk
                L2TPv3. This transport allows connecting a VM to a VM,
                VM to a router and even VM to Host. It is a nearly-universal
                standard (RFC3391). Note - this implementation uses static
                pre-configured tunnels (same as the Linux kernel).
                use 'src=' to specify source address
                use 'dst=' to specify destination address
                use 'udp=on' to specify udp encapsulation
                use 'srcport=' to specify source udp port
                use 'dstport=' to specify destination udp port
                use 'ipv6=on' to force v6
                L2TPv3 uses cookies to prevent misconfiguration as
                well as a weak security measure
                use 'rxcookie=0x012345678' to specify a rxcookie
                use 'txcookie=0x012345678' to specify a txcookie
                use 'cookie64=on' to set cookie size to 64 bit, otherwise 32
                use 'counter=off' to force a 'cut-down' L2TPv3 with no counter
                use 'pincounter=on' to work around broken counter handling in peer
                use 'offset=X' to add an extra offset between header and data
-netdev socket,id=str[,fd=h][,listen=[host]:port][,connect=host:port]
                configure a network backend to connect to another network
                using a socket connection
-netdev socket,id=str[,fd=h][,mcast=maddr:port[,localaddr=addr]]
                configure a network backend to connect to a multicast maddr and port
                use 'localaddr=addr' to specify the host address to send packets from
-netdev socket,id=str[,fd=h][,udp=host:port][,localaddr=host:port]
                configure a network backend to connect to another network
                using an UDP tunnel
-netdev vhost-user,id=str,chardev=dev[,vhostforce=on|off]
                configure a vhost-user network, backed by a chardev 'dev'
-netdev hubport,id=str,hubid=n[,netdev=nd]
                configure a hub port on the hub with ID 'n'
-nic [tap|bridge|user|l2tpv3|vhost-user|socket][,option][,...][mac=macaddr]
                initialize an on-board / default host NIC (using MAC address
                macaddr) and connect it to the given host network backend
-nic none       use it alone to have zero network devices (the default is to
                provided a 'user' network connection)
-net nic[,macaddr=mac][,model=type][,name=str][,addr=str][,vectors=v]
                configure or create an on-board (or machine default) NIC and
                connect it to hub 0 (please use -nic unless you need a hub)
-net [user|tap|bridge|socket][,option][,option][,...]
                old way to initialize a host network interface
                (use the -netdev option if possible instead)

Character device options:
-chardev help
-chardev null,id=id[,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev socket,id=id[,host=host],port=port[,to=to][,ipv4][,ipv6][,nodelay][,reconnect=seconds]
         [,server][,nowait][,telnet][,websocket][,reconnect=seconds][,mux=on|off]
         [,logfile=PATH][,logappend=on|off][,tls-creds=ID] (tcp)
-chardev socket,id=id,path=path[,server][,nowait][,telnet][,websocket][,reconnect=seconds]
         [,mux=on|off][,logfile=PATH][,logappend=on|off] (unix)
-chardev udp,id=id[,host=host],port=port[,localaddr=localaddr]
         [,localport=localport][,ipv4][,ipv6][,mux=on|off]
         [,logfile=PATH][,logappend=on|off]
-chardev msmouse,id=id[,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev vc,id=id[[,width=width][,height=height]][[,cols=cols][,rows=rows]]
         [,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev ringbuf,id=id[,size=size][,logfile=PATH][,logappend=on|off]
-chardev file,id=id,path=path[,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev pipe,id=id,path=path[,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev pty,id=id[,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev stdio,id=id[,mux=on|off][,signal=on|off][,logfile=PATH][,logappend=on|off]
-chardev braille,id=id[,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev serial,id=id,path=path[,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev tty,id=id,path=path[,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev parallel,id=id,path=path[,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev parport,id=id,path=path[,mux=on|off][,logfile=PATH][,logappend=on|off]
-chardev spicevmc,id=id,name=name[,debug=debug][,logfile=PATH][,logappend=on|off]
-chardev spiceport,id=id,name=name[,debug=debug][,logfile=PATH][,logappend=on|off]

Bluetooth(R) options:
-bt hci,null    dumb bluetooth HCI - doesn't respond to commands
-bt hci,host[:id]
                use host's HCI with the given name
-bt hci[,vlan=n]
                emulate a standard HCI in virtual scatternet 'n'
-bt vhci[,vlan=n]
                add host computer to virtual scatternet 'n' using VHCI
-bt device:dev[,vlan=n]
                emulate a bluetooth device 'dev' in scatternet 'n'

TPM device options:
-tpmdev passthrough,id=id[,path=path][,cancel-path=path]
                use path to provide path to a character device; default is /dev/tpm0
                use cancel-path to provide path to TPM's cancel sysfs entry; if
                not provided it will be searched for in /sys/class/misc/tpm?/device
-tpmdev emulator,id=id,chardev=dev
                configure the TPM device using chardev backend

Linux/Multiboot boot specific:
-kernel bzImage use 'bzImage' as kernel image
-append cmdline use 'cmdline' as kernel command line
-initrd file    use 'file' as initial ram disk
-dtb    file    use 'file' as device tree image

Debug/Expert options:
-fw_cfg [name=]<name>,file=<file>
                add named fw_cfg entry with contents from file
-fw_cfg [name=]<name>,string=<str>
                add named fw_cfg entry with contents from string
-serial dev     redirect the serial port to char device 'dev'
-parallel dev   redirect the parallel port to char device 'dev'
-monitor dev    redirect the monitor to char device 'dev'
-qmp dev        like -monitor but opens in 'control' mode
-qmp-pretty dev like -qmp but uses pretty JSON formatting
-mon [chardev=]name[,mode=readline|control][,pretty[=on|off]]
-debugcon dev   redirect the debug console to char device 'dev'
-pidfile file   write PID to 'file'
-singlestep     always run in singlestep mode
--preconfig     pause QEMU before machine is initialized (experimental)
-S              freeze CPU at startup (use 'c' to start execution)
-realtime [mlock=on|off]
                run qemu with realtime features
                mlock=on|off controls mlock support (default: on)
-overcommit [mem-lock=on|off][cpu-pm=on|off]
                run qemu with overcommit hints
                mem-lock=on|off controls memory lock support (default: off)
                cpu-pm=on|off controls cpu power management (default: off)
-gdb dev        wait for gdb connection on 'dev'
-s              shorthand for -gdb tcp::1234
-d item1,...    enable logging of specified items (use '-d help' for a list of log items)
-D logfile      output log to logfile (default stderr)
-dfilter range,..  filter debug output to range of addresses (useful for -d cpu,exec,etc..)
-L path         set the directory for the BIOS, VGA BIOS and keymaps
-bios file      set the filename for the BIOS
-enable-kvm     enable KVM full virtualization support
-enable-hax     enable HAX virtualization support
-xen-domid id   specify xen guest domain id
-xen-create     create domain using xen hypercalls, bypassing xend
                warning: should not be used when xend is in use
-xen-attach     attach to existing xen domain
                xend will use this when starting QEMU
-xen-domid-restrict     restrict set of available xen operations
                        to specified domain id. (Does not affect
                        xenpv machine type).
-no-reboot      exit instead of rebooting
-no-shutdown    stop before shutdown
-loadvm [tag|id]
                start right away with a saved state (loadvm in monitor)
-daemonize      daemonize QEMU after initializing
-option-rom rom load a file, rom, into the option ROM space
-rtc [base=utc|localtime|<datetime>][,clock=host|rt|vm][,driftfix=none|slew]
                set the RTC base and clock, enable drift fix for clock ticks (x86 only)
-icount [shift=N|auto][,align=on|off][,sleep=on|off,rr=record|replay,rrfile=<filename>,rrsnapshot=<snapshot>]
                enable virtual instruction counter with 2^N clock ticks per
                instruction, enable aligning the host and virtual clocks
                or disable real time cpu sleeping
-watchdog model
                enable virtual hardware watchdog [default=none]
-watchdog-action reset|shutdown|poweroff|inject-nmi|pause|debug|none
                action when watchdog fires [default=reset]
-echr chr       set terminal escape character instead of ctrl-a
-virtioconsole c
                set virtio console
-show-cursor    show cursor
-tb-size n      set TB size
-incoming tcp:[host]:port[,to=maxport][,ipv4][,ipv6]
-incoming rdma:host:port[,ipv4][,ipv6]
-incoming unix:socketpath
                prepare for incoming migration, listen on
                specified protocol and socket address
-incoming fd:fd
-incoming exec:cmdline
                accept incoming migration on given file descriptor
                or from given external command
-incoming defer
                wait for the URI to be specified via migrate_incoming
-only-migratable     allow only migratable devices
-nodefaults     don't create default devices
-chroot dir     chroot to dir just before starting the VM
-runas user     change to user id user just before starting the VM
                user can be numeric uid:gid instead
-sandbox on[,obsolete=allow|deny][,elevateprivileges=allow|deny|children]
          [,spawn=allow|deny][,resourcecontrol=allow|deny]
                Enable seccomp mode 2 system call filter (default 'off').
                use 'obsolete' to allow obsolete system calls that are provided
                    by the kernel, but typically no longer used by modern
                    C library implementations.
                use 'elevateprivileges' to allow or deny QEMU process to elevate
                    its privileges by blacklisting all set*uid|gid system calls.
                    The value 'children' will deny set*uid|gid system calls for
                    main QEMU process but will allow forks and execves to run unprivileged
                use 'spawn' to avoid QEMU to spawn new threads or processes by
                     blacklisting *fork and execve
                use 'resourcecontrol' to disable process affinity and schedular priority
-readconfig <file>
-writeconfig <file>
                read/write config file
-no-user-config
                do not load default user-provided config files at startup
-trace [[enable=]<pattern>][,events=<file>][,file=<file>]
                specify tracing options
-enable-fips    enable FIPS 140-2 compliance
-msg timestamp[=on|off]
                change the format of messages
                on|off controls leading timestamps (default:on)
-dump-vmstate <file>
                Output vmstate information in JSON format to file.
                Use the scripts/vmstate-static-checker.py file to
                check for possible regressions in migration code
                by comparing two such vmstate dumps.
-enable-sync-profile
                enable synchronization profiling

Generic object creation:
-object TYPENAME[,PROP1=VALUE1,...]
                create a new object of type TYPENAME setting properties
                in the order they are specified.  Note that the 'id'
                property must be set.  These objects are placed in the
                '/objects' path.

During emulation, the following keys are useful:
ctrl-alt-f      toggle full screen
ctrl-alt-n      switch to virtual console 'n'
ctrl-alt        toggle mouse and keyboard grab

When using -nographic, press 'ctrl-a h' to get some help.

See <https://qemu.org/contribute/report-a-bug> for how to report bugs.
More information on the QEMU project at <https://qemu.org>.
wanghuozhu@dlserver:~/ws/other/panda/x86_64-softmmu$ 
```