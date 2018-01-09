setupgrubfornfsinstall
======================

setupgrubfornfsinstall is a dialog based shell script to prepare remote network
installations. The script downloads kernel and initrd of the distribution and
either creates a boot loader entry for easy reinstallation of physical systems
or prepares a disk image for installation in qemu/kvm.

[Screenshots](screenshots/screenshots.md)

Features
--------

- install openSUSE, Fedora, Ubuntu, Slackware
- qemu/kvm support, just run setupgrubfornfsinstall with option --qemu.
- browse installation sources offered via SLP in your LAN
- browse nfs exports (special config file needed then)
- support for nfs, ftp and http
- supports grub2, grub and lilo (the latter mostly untested nowadays though)
- supports ssh/vnc installation parameters (SUSE only)

Run
---

	sudo ./setupgrubfornfsinstall

or for qemu
  
	./setupgrubfornfsinstall --qemu

Hints for headless remote installations
---------------------------------------

- add panic=10 to the boot parameters so the kernel reboots if
  something goes wrong that causes a kernel panic.
- use grubonce to tell grub to make the installation entry the
  default only once. This way the system will boot the old
  installation upon reboot if you
  don’t overwrite the boot loader.
