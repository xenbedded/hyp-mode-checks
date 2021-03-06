
# Simple Hypervisor Check Stub

This simple stub allows you to extend your kernel with an easy
message to identify its boot mode. Should work with any Xen-compatible
kernel; but isn't needed if your kernel is new enough.

- ARM32: 3.7+ will print this out for you, so this isn't needed!
- ARM64: 4.3+ will print this out for you, so this isn't needed!
- Earlier kernels: try this!

## Instructions

As the relevant mode information isn't exported, this stub has to be
linked into your kernel. Luckily, that's fairly easy. Copy this source
file to the "drivers/misc" folder of your kernel source tree, and
then add it to the relevant Makefile.

```
# Copy the file in...
$ cp hypcheck.o <kernel-path>/drivers/misc/

# ... add it to our build...
$ echo "obj-y += hypcheck.o" >> <kernel-path>/drivers/misc/Makefile

# ... and (re)build our kernel.
$ cd <kernel-path>
$ make
```
