Download Driver Package
#######################

Before customizing file system, you need prepare the driver package of your ROScube device.

ADLINK has provided the driver package.

1. Go to the Device Website
---------------------------

Assuming the using device is **ROScube-X-58G**.

Go to it's `device website <https://www.adlinktech.com/Products/ROS2_Solution/ROS2_Controller/ROScube-X?lang=zh-hant>`_.


2. Go to the Driver
-------------------

Go the Driver from Technical Resources.

.. image:: images/device-web.png
  :width: 80%
  :align: center 

Then you will see the driver packages in this page. 

.. image:: images/driver-packages.png
  :width: 80%
  :align: center 

3. Download the Driver package
------------------------------

Download the driver package which you want. 

For example, we download the ``RQX-58G Jetpack 4.6, L4T 32.6.x driver package``.

.. note:: 

    Before downloading, you might log in or create a account.

4. Unarchive the driver package
-------------------------------

After downloading, you could use tar tool to unarchive **driver package**.

.. code-block:: bash
    
    tar xvf <ROScube device>-Driver-Package.tar.gz