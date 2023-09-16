.. _camera_driver:

Camera Driver Installation
##########################

You need to install dedicated camera driver.

Please ask ADLINK or the camera vendor for the latest camera driver.

1. Install Camera Driver
-------------------------

To install camera driver, please follow the commands below:

.. code:: bash
    
    sudo apt update
    sudo apt install -f <camera_driver.deb>
    
    # Examples:
    # 
    # [Tier IV]
    # sudo apt install -f tier4-camera-gmsl_1.3.0_arm64.deb
    # 
    # [Leopard AR0233]
    # sudo apt install -f roscube-gmsl-serdes_0.9.3_arm64.deb
    
.. warning::

    | You can only install one camera driver in ROScube to avoid conflicts.
      If there are two or more, please remove them which you don't use.
    | To remove unused camera driver, please use ``sudo apt remove --purge <camera driver>``


2. Apply Device Tree
-------------------------

To enable the camera driver, you have to apply the device tree settings.
Before applying, please use below command to list available modules:

.. code:: bash

    sudo /opt/nvidia/jetson-io/config-by-hardware.py --list

.. image:: images/config-hardware-list.png
  :width: 80%
  :align: center

The camera device tree overlay may be located in different headers depends on the BSP and Jetpack version.

.. image:: images/config-hardware-list-tier4.png
  :width: 80%
  :align: center

To apply the device tree setings, please follow the commands below:

For Jetpack 4.6, 5.0, and later:
================================

If the device tree is located in "Header 1", please enter below command:

.. code:: bash

    sudo /opt/nvidia/jetson-io/config-by-hardware.py -n 1='<YOUR_CAMERA_DEVICE_TREE_OVERLAY>'
    # Examples:
    #
    # [Tier IV C1]
    # sudo /opt/nvidia/jetson-io/config-by-hardware.py -n 1='TIERIV ISX021 GMSL2 Camera Device Tree Overlay'
    #
    # [Leopard AR0233]
    # sudo /opt/nvidia/jetson-io/config-by-hardware.py -n 1='Leopard AR0233 RAW GMSL2 Camera Device Tree Overlay'


Otherwise, the device tree is located in "Header 2", please enter below command:

.. code:: bash

    sudo /opt/nvidia/jetson-io/config-by-hardware.py -n 2='<YOUR_CAMERA_DEVICE_TREE_OVERLAY>'

.. image:: images/config-hardware-name.png
  :width: 80%
  :align: center


For Jetpack 4.5:
================


Download the patched :download:`libgstnvarguscamerasrc.so <file/libgstnvarguscamerasrc.so>` and replace this file with the original one.

.. code:: bash

    sudo rm /usr/lib/aarch64-linux-gnu/gstreamer-1.0/libgstnvarguscamerasrc.so
    sudo mv libgstnvarguscamerasrc.so /usr/lib/aarch64-linux-gnu/gstreamer-1.0/libgstnvarguscamerasrc.so

Then, apply device tree into your system.

.. code:: bash

    sudo /opt/nvidia/jetson-io/config-by-hardware.py -n '<YOUR_CAMERA_DEVICE_TREE_OVERLAY>'

3. Reboot
----------

Finally, please **reboot** system for the new settings to take effect.
    
.. code:: bash

    sudo reboot

4. Check Camera
----------------

After rebooting, you can check if the cameras are available.

Please use the following command to check:

.. code:: bash

    ls /dev/video*

.. image:: images/dev-video.png
  :width: 80%
  :align: center


.. warning::

    | If there are no video devices, make sure cameras are connected.
    | And check the error logs by typing the command ``dmesg | egrep -i 'max9295|max9296'`` in terminal.
