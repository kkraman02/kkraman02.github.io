Backup and Restore
##################

The tutorial will guide you how to backup and restore system image.

.. note:: 

    The target machine must be connected to your **Host PC** over USB and entered into **recovery mode**.

+--------------------+-----------------------+
|Model               |Target Name            |
+====================+=======================+
|RQX-590             |jetson-agx-orin-rqx59x |
+--------------------+-----------------------+
|RQX-580             |rqx_580                |
+--------------------+-----------------------+
|RQX-58G             |rqx_58g                |
+--------------------+-----------------------+
|NPN-1 (Pico Nano)   |npn1                   |
+--------------------+-----------------------+
|NPN-2 (Pico AGX NX) |npn2                   | 
+--------------------+-----------------------+

1. Cloning the Image
^^^^^^^^^^^^^^^^^^^^

.. code-block:: bash

    cd <driver package>
    sudo ./flash.sh -r -k APP -G backup.img <target name> mmcblk0p1

This command actually creates two image files: ``backup.img`` and ``backup.img.raw``. 

| ``backup.img.raw`` contains raw data read from the target's APP partition, it has exactly the same size as APP partition. 
| ``backup.img`` is a sparsed image, it has a much smaller size and can speed up the restoring step. 

2. Copy the backup image to flashing directory
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

copy the ``backup.img`` file to the bootloader folder. 

.. code-block:: bash
    
    sudo cp backup.img bootloader/system.img

3. Restoring the Image
^^^^^^^^^^^^^^^^^^^^^^

The recommended way to restore multiple units with different serial numbers is to save the image above as "system.img" and use the head L4T flashing script, ``flash.sh``, with the -r option (to reuse your backed-up system.img without rebuilding the vanilla image from scratch): 

.. code-block:: bash

    sudo ./flash.sh -r -k APP <target name> mmcblk0p1

.. note:: 

    Each flashing procedure might take 8 ~ 10 minutes.