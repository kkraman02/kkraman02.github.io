Customize System FileSystem
###########################

Customize file system on **Host PC**. 

1. Prepare Filesystem
^^^^^^^^^^^^^^^^^^^^^

| Driver package allows users to customize their filesystem. 
| Driver package provides a script (create_image.sh) to create a board specific image base on several rootfs selection, here's what we support.

So you need to prepare these items:

    * Driver package
    * Rootfs Binaries

Download Rootfs Binaries
------------------------

The file system we use here is **NVIDIA Sample Filesystem**.

Please download the correct L4T version from `NVIDIA Developer <https://developer.nvidia.com/embedded/linux-tegra-archive>`_.

| For example, if you are using ADLINK provided driver package 32.6.1, you should download from `Jetson Linux R32.6.1 Release Page <https://developer.nvidia.com/embedded/linux-tegra-r3261>`_.
| Download ``Sample Root Filesystem`` according to your **ROScube device**.

.. image:: images/L4T-driver.png
  :width: 50%
  :align: center

Create Image
------------

After you download rootfs binary successfully, put the binary under the **driver package folder**. 

Then, run ``./create_image.sh`` to create image.

.. code-block:: bash
    
    cd <driver package>
    sudo ./create_image.sh nvidia_sample_rootfs


2. Modify Filesystem under root
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Users can chroot into filesystem, and install packages or put files to filesystem. That allows user to put their software and configurations into rootfs.

1. Mount host environment to filesystem. 

.. code-block:: bash

    cd <driver package>
    cd rootfs
    sudo cp /usr/bin/qemu-aarch64-static usr/bin/
    sudo mount --bind /dev/ dev/
    sudo mount --bind /sys/ sys/
    sudo mount --bind /proc/ proc/

    # Copy host environment dns settings.
    sudo cp /etc/resolv.conf etc/resolv.conf.host
    sudo mv etc/resolv.conf etc/resolv.conf.saved
    sudo mv etc/resolv.conf.host etc/resolv.conf

2. Now you can chroot into filesystem and modify filesystem.

.. code-block:: bash
    
    # Using chroot
    sudo LC_ALL=C LANG=C.UTF-8 chroot . /bin/bash
    
    apt update
    apt install wget vim

    # Also you can install other packages which you want
    apt install nvidia-jetpack

3. Once you finish modification, you can exit chroot environment by pressing ctrl+D. Then, remove cache files, e.g. apt cache to save storage space.

.. code-block:: bash

    # Exit chroot 
    exit

    sudo umount ./proc
    sudo umount ./sys
    sudo umount ./dev
    sudo rm usr/bin/qemu-aarch64-static
    
    # Restore dns setting.
    sudo rm etc/resolv.conf
    sudo mv etc/resolv.conf.saved etc/resolv.conf

    # Remove caches and logging files.

    sudo rm -rf var/lib/apt/lists/*
    sudo rm -rf dev/*
    sudo rm -rf var/log/*
    sudo rm -rf var/tmp/*
    sudo rm -rf var/cache/apt/archives/*.deb
    sudo rm -rf tmp/*