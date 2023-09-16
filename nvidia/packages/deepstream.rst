DeepStream SDK
##############

Here shows:

    * How to install the Deepstream SDK
    * The usage of DeepStream SDK Example.

1.  DeepStream SDK Installation
-------------------------------

Download the DeepStream for Jetson from `NVIDIA DEVELOPER <https://developer.nvidia.com/deepstream-getting-started>`_.

After downloading, you can **double click** the  `deb file` or follow the command to install:

.. code:: 

    sudo apt install ./deepstream_sdk_<version>_arm64.deb

.. note:: 
    
    | Please refer `jetson software version table` to download proper DeepStream SDK version.
    | DeepStream **6.0** for JetPack **4.6**.
    | DeepStream **5.0** for JetPack **4.5**.

.. note:: 

    You may need to login or create a NVIDIA account, when you download. 

2.  DeepStream SDK Example Usage
--------------------------------

After DeepStream SDK installation, there will be some DeepStream examples and tools available under ``/opt/nvidia/deepstream/deepstream-<version>``.

DeepStream Sample App
*********************

.. code:: 

    deepstream-app -c /opt/nvidia/deepstream/deepstream-<version>/samples/configs/deepstream-app/<config file>

deepstream ``<version>`` follows you installed before, and ``<config file>`` could be replaced with the following table:

+--------------------+--------------------------------------------------------------------+
| Model              | Config File                                                        |
+====================+====================================================================+
| RQX-580            | source12_1080p_dec_infer-resnet_tracker_tiled_display_fp16_tx2.txt |
+--------------------+--------------------------------------------------------------------+
| RQX-58G            | source12_1080p_dec_infer-resnet_tracker_tiled_display_fp16_tx2.txt |
+--------------------+--------------------------------------------------------------------+
| NPN-1 (Pico Nano)  | source8_1080p_dec_infer-resnet_tracker_tiled_display_fp16_nano.txt |
+--------------------+--------------------------------------------------------------------+
| NPN-2 (Pico AGX NX)| source12_1080p_dec_infer-resnet_tracker_tiled_display_fp16_tx2.txt |
+--------------------+--------------------------------------------------------------------+


.. image:: images/deepstream-demo.png
  :width: 80%
  :align: center