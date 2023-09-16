Driver Packages Usage
#####################

The tutorial will guide you how to customize the BSP file system on your **Host PC**.

Before customizing file system to ROScube, you should prepare the following items:

    * Host PC with Ubuntu 18.04 or 20.04 operating system.
    * A good quality micro-usb for connecting to ROScube.
    * Driver Package of ROScube


Driver Package is a package contains several assets that runs on host computer, which allows you to do:

    * Customize system file system.
    * Flash system image to target machine.
    * System image backup and restore.
    * Create a custom mfi image.

User can modify their rootfs on their host computer before flashing the image to target machine.

**Table of Contents:**

.. toctree::
   :maxdepth: 1

   driver_packages.rst
   customize_filesystem.rst
   flash_system.rst
   backup_restore.rst