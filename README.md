## Test kernel path 

Clone kernel source and apply patch
```
$ git clone https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux.git
$ cd linux
$ git fetch origin linux-6.4.y:linux-6.4.y
$ git checkout -b my-linux-experiment/linux-6.4.y
$ git am /path/to/0001-x86-module-add-Kconfig-options-for-disallow-unload-k.patch
```
Create defconfig and check kernel option
```
$ mkdir ../build_x86
$ cp -v /boot/config-$(uname -r) ../build_x86/.config
$ make O=../build_x86/ olddefconfig
$ make O=../build_x86/ menuconfig
```

![Alt text](screenshot_menuconfig.png?raw=true "Kernel-menuconfig")
