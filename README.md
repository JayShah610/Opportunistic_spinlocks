# Opportunistic_spinlocks


1) Download the kernel version from https://www.kernel.org/
2) Extract the files
3) Open folder
4) Go to arch/x86/include/asm
5) Replace our file with old spinlock.
6) Follow the following steps to compile and boot into the new kernel.

**For kernel compilation**

1) tar xvf linux-4.4.274.tar.xz  // Unzip folder
2) sudo apt-get install git fakeroot build-essential ncurses-dev xz-utils libssl-dev bc flex libelf-dev bison   // Install essential packages
3) cd linux-4.4.274
4) cp -v /boot/config-$(uname -r) .config  //copy existing configuration file
5) make menuconfig 
  a) general setup
  b) enabled Automatically append version information to the version string
6) make  // building kernel
7) sudo make modules_install // install required modules
8) sudo make install
9) GRUB bootloader is the first program that runs when system powers on, Changed GRUB file so that new kernel boots.
10) uname -mrs  // to verify the kernel version
