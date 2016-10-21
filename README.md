mainline-linux kernel builder
=============================

This is based on RCN's kernel build scripts for arm devices, modified to build
native x86_64 kernels (mainly for laptops running hot with stock debian kernel).

The main config variables in version.sh are just hacked in at the moment; more
flexible/transparent behavior is planned.  For now it supports only ARM or
x86_64 (AMD 64-bit) kernels; Select a *-amd branch to try the laptop kernel build.

Host detection has basic Gentoo support added, but you'll need to manually
install the required (normal) dependencies plus dpkg and fakeroot to build
a deb kernel package.
