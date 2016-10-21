This is just a set of scripts to rebuild a known working kernel for both ARM
devices and funky AMD laptops (mainly because of overheating and the need to
build a custom and/or packaged kernel on different build host.  Also you get
the latest linux-stable.

The main config variables in version.sh are just hacked in at the moment;
more flexible/transparent behavior is planned. For now it supports only ARM
or x86_64 (AMD 64-bit) kernels.

Host detection has basic Gentoo support added, but you'll need to manually 
install the required (normal) dependencies plus dpkg and fakeroot to build
a deb kernel package.

Select the *-amd branch to try the laptop kernel build, or versioned branch
for an ARM kernel.

For bugs please use the issue tracker:

https://github.com/sarnold/multi_arch-mainline-linux/issues

ARM Dependencies: GCC ARM Cross ToolChain

Linaro:
http://www.linaro.org/downloads/

x86_64 Dependencies: GCC Native ToolChain

Gentoo: of course!  Also, lsb-release, dpkg, and fakeroot.

Debian/Ubuntu: apt-get install build-essential (or install gcc). Other build
tools should be pre-installed; the script will check for required packages.

Common Dependencies: Linux Kernel Source

This git repo contains just scripts/patches to build a specific kernel for
some ARM devices and x86_64 machines. The kernel source will be downloaded
when you run any of the build scripts.

By default this script will clone the linux-stable tree:
https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git
to: ${DIR}/ignore/linux-src:

If you've already cloned torvalds tree and would like to save some hard drive
space, just modify the LINUX_GIT variable in system.sh to point to your current
git clone directory.

Build Kernel Image:

```
./build_kernel.sh
```

Optional: Build Debian Package:

```
./build_deb.sh
```

Development/Hacking:

first run (to setup baseline tree): ./build_kernel.sh
then modify files under KERNEL directory
then run (to rebuild with your changes): ./tools/rebuild.sh


