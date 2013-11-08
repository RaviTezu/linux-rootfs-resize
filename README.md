linux-rootfs-resize
===================

Rework of my previous project, that was limited only to CentOS 6.x.

This tool creates new initrd (initramfs) image with ability to resize root filesystem 
over available space. Tipically you need this when you provision your virtual machine on 
OpenStack cloud for the first time (your image becomes flavor aware)

This code was successfuly tested on: CentOS 6.4, Debian 6 and Debian 7.2

LIMITATIONS:

    Roofs on extended partition is not tested/supported. So far my testing suggest that 'growpart' can't handle them!

DEPENDENCIES:

    cloud-utils (https://launchpad.net/cloud-utils)

CentOS 6:

    supports physical and LVM partitions

Debian 6 and 7:

    for now, tool can only resize NON LVM partition (it DOES NOT support LVM!)

INSTALL: 

    Install git, clone this project on your machine, make 'install' executable and run it.

On CentOS:

    yum install git
    git clone https://github.com/flegmatik/linux-rootfs-resize.git
    cd linux-rootfs-resize
    chmod +x install
    ./install

Tool is designed in modular fassion so support for other distributions can be added without much work (I hope).
