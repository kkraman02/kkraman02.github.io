.. _gmsl_camera:

GMSL2 Camera
#############

Supported model: ROScube **RQX-58G** and **RQX-59G** series only

**RQX-58G/59G** is one of the **ROScubeX series model**, which extends **GMSL2** standard protocol cameras.

**GMSL2** is SerDes protocol which provides high bandwidth and low latency video streaming for high resolution cameras.

Unlike IP camera or other USB UVC standard cameras,
GMSL2 camera provide RAW frame which has not been compressed by certain encoding algothrim, e.g. H.264 or H.265.

.. warning::

    GMSL2 camera does not support hot-plugging.
    Please connect the camera before bootup, or ROScube-X can not detect it.

**Supported GMSL2 camera**

The following table is the GMSL2 camera support list.

+-----------------------+-----------------+--------------------+-----------+-----------------+---------------------+
| Camera Model          | Vendor          | Image Sensor       | ISP       | Video Framework | Note                |
+=======================+=================+====================+===========+=================+=====================+
| Tier IV C1            | Tier IV         | Sony ISX021        | ISX021    | V4L2            |                     |
+-----------------------+-----------------+--------------------+-----------+-----------------+---------------------+
| Tier IV C2            | Tier IV         | Sony IMX490        | GW5300    | V4L2            |                     |
+-----------------------+-----------------+--------------------+-----------+-----------------+---------------------+
| oToCAM260ISP          | oToBrite        | Sony IMX490        | GW5300    | V4L2            | Tested by oToBrite  |
+-----------------------+-----------------+--------------------+-----------+-----------------+---------------------+
| oToCAM264ISP          | oToBrite        | Sony IMX390        | GW5200    | V4L2            | Tested by oToBrite  |
+-----------------------+-----------------+--------------------+-----------+-----------------+---------------------+
| SG8-OX08BC-5300-GMSL2 | SENSING         | OmniVision OX08B40 | GW5300    | V4L2            | Tested by customers |
+-----------------------+-----------------+--------------------+-----------+-----------------+---------------------+
| LI-AR0233-GMSL2       | Leopard Imaging | ONSEMI AR0233AT    |           | NVIDIA Argus    |                     |
+-----------------------+-----------------+--------------------+-----------+-----------------+---------------------+

**Table of Contents:**

.. toctree::
   :maxdepth: 1

   system_diagram.rst
   camera_driver.rst
   camera_usage.rst
   frame_sync.rst