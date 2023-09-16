.. _camera_usage:

Camera Usage
############

GStreamer
---------

Different video frameworks have different methods to run cameras.
You should check which video framework your camera is and select the right method.

Here we show how to run cameras with gstreamer plugin based on V4L2 or NVIDIA Argus.

If your camera has ISP, then you sholud use v4l2src; otherwise, use nvarguscamerasrc for the cameras without ISP.

v4l2src plugin
==============

To use V4L2, you can read video device under ``/dev/`` directly.
The camera will be listed like ``/dev/videoX``, while X is from 0-7.

To read camera 1 by gstreamer:

.. code:: bash

    # Example for Tier IV C1 video0
    gst-launch-1.0 -e v4l2src device=/dev/video0 ! 'video/x-raw,format=UYVY,width=1920,height=1280' ! videoconvert ! fpsdisplaysink video-sink=xvimagesink sync=false

.. image:: images/tier4_video0.png
  :width: 100%
  :align: center

nvarguscamerasrc plugin
=======================

Cameras without ISP can use **Argus API** to preview the camera's video streaming, 
or you can use **GStreamer nvarguscamerasrc plugin** to preview the video streaming.

Make sure you have modified **sensor-id=0** on the following command.

+---------------+-----------+
| Camera Number | Sensor ID |
+===============+===========+     
| Camera 1      | 0         |
+---------------+-----------+
| Camera 2      | 1         |
+---------------+-----------+
| Camera 3      | 2         |
+---------------+-----------+
| Camera 4      | 3         |
+---------------+-----------+
| Camera 5      | 4         |
+---------------+-----------+
| Camera 6      | 5         |
+---------------+-----------+
| Camera 7      | 6         |
+---------------+-----------+
| Camera 8      | 7         |
+---------------+-----------+

i. Open a terminal and type command to open ``camera 1's video`` streaming.

.. code:: bash

    # Example for AR0233 w/o ISP
    gst-launch-1.0 -e nvarguscamerasrc sensor-id=0 ! 'video/x-raw(memory:NVMM), width=2048, height=1280, framerate=30/1' ! nvvidconv ! 'video/x-raw, format=(string)RGBA' ! videoconvert ! fpsdisplaysink video-sink=xvimagesink sync=false


ii. Open **another** terminal and type command to ``open camera 2's video`` streaming.

.. code:: bash

    gst-launch-1.0 -e nvarguscamerasrc sensor-id=1 ! 'video/x-raw(memory:NVMM), width=2048, height=1280, framerate=30/1' ! nvvidconv ! 'video/x-raw, format=(string)RGBA' ! videoconvert ! fpsdisplaysink video-sink=xvimagesink sync=false

.. image:: images/gst-test.png
  :width: 80%
  :align: center

If successful, you will see two windows from different cameras, like below.

.. image:: images/gst-preview.png
  :width: 80%
  :align: center

.. warning::

    If you find that Argus plugin can't operate well, you can restart nvargus-daemon.
    ``sudo systemctl restart nvargus-daemon.service``

v4l-utils
---------

v4l2-ctl offers a way to start camera stream and evaluate the FPS without showing the real images.

.. code:: bash

    v4l2-ctl -d /dev/video0  --set-ctrl bypass_mode=0 --stream-mmap
    
.. image:: images/v4l2-ctl.png
  :width: 100%
  :align: center