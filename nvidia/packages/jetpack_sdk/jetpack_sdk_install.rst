Jetpack SDK Installation
########################

Since NVIDIA L4T 32.4.x support L4T OTA, users can download NVIDIA Jetpack from NVIDIA’s official APT
repository.
For ROScube NVIDIA platform users, you can use ``apt`` to install NVIDIA Jetpack compoments, e.g. CUDA, tensorrt.

1. Install the whole JetPack SDK
--------------------------------
Assume that your Jetson developer kit has been flashed and is running **L4T 32.4.x**,
the following commands will install **all** ``JetPack``.

.. code-block:: bash

    sudo apt update
    sudo apt install nvidia-jetpack

.. warning:: 

    | It's **not suggested** to install ``nvidia-jetpack`` directly, because nvidia-jetpack is a meta package which will install **all JetPack SDK** compoments which occupy **8GB**.
    | You can only install ``particular`` JetPack SDK compoment.

2. Install particular JetPack SDK compoment.
--------------------------------------------
If we only want to use parts of JetPack SDK (e.g. CUDA) instead the whole JetPack SDK,
we can just install related library.

.. code-block:: bash

    # If we just want to use CUDA library
    sudo apt update
    sudo apt install nvidia-cuda nvidia-l4t-cuda
