Mounting FileSystem From SD Card
################################

When inserting a **SD card** to ROScube, the storage will be appeared as a ``/dev/mmcblk1`` storage.

1. Format SD card to EXT4 filesystem.
-------------------------------------

.. code-block:: bash

    cd rootOnStorage/sdmmc
    sudo ./copy-rootfs-sdmmc.sh

.. image:: images/sdmmc-copy.png
  :width: 80%
  :align: center

.. note:: 
    
    After finishing, you can see ``to-chk=0/*``.

2. Setup the service. 
---------------------

This will copy the .service file to the correct location, and install a startup script to set the rootfs to the SD card.

.. code-block:: bash

    sudo ./setup-service.sh

.. image:: images/sdmmc-setup.png
  :width: 80%
  :align: center

.. note:: 
    
    After setting up the service, **reboot** for the changes to take effect.
