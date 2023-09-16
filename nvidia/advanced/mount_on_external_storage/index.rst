Mount rootfs on External Storage
################################

ROScube can mount filesystem from external storage. Available types are:

    * SD card
    * NVMe M.2 SSD

ADLINK provides a tool to `mount rootfs on external storage <https://github.com/Adlink-ROS/rootOnStorage>`_.
Switch the rootfs to a NVMe SSD or SDMMC on the ROScube series. 

+------------------+---------+--------------+
|Device            | SD Card | NVMe M.2 SSD |
+==================+=========+==============+
|ROScube-X         |    V    |      V       |
+------------------+---------+--------------+
|ROScube-Pico-NX   |    V    |      V       |
+------------------+---------+--------------+
|ROScube-Pico-Nano |    V    |              |
+------------------+---------+--------------+

These scripts install a service which runs at startup to point the rootfs to NVMe installed on ``/dev/nvme0`` or SDMMC installed on ``/dev/mmcblk1``.

**Parepare the rootOnStorage files from Github.**

.. code-block:: bash

  git clone https://github.com/Adlink-ROS/rootOnStorage.git

**Table of Contents:**

.. toctree::
   :maxdepth: 1

   mounting_sdmmc.rst
   mounting_nvme.rst