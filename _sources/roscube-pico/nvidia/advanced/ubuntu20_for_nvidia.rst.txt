Ubuntu 20.04 for NVIDIA
#######################

NVIDIA Jetpack 4.x is based on Ubuntu 18.04, and it's inconvenient when we want to use Ubuntu 20.04.
For example, the LTS of ROS 1 noetic and ROS 2 foxy only support Ubuntu 20.04.
There are many NVIDIA and ROS users struggling with the problem.
Before NVIDIA Jetpack 5, which is Ubuntu 20.04, is released,
docker container is a good solution to the issue.

However, there are too many tricky settings to run container on NVIDIA platform, especially when you want to use CUDA.
To simplify the usage, ADLINK provides the following guide to install containers.

Flash the image
---------------

Download Jetpack 4.6 from ADLINK official website and flash the ROScube.
Follow the tutorial based on your ROScube platform:

* ROScube-X: https://adlink-ros.github.io/roscube-doc/roscube-x/flash_image/flash_mfi.html
* ROScube-Pico (board level): https://adlink-ros.github.io/roscube-doc/roscube-pico/flash_image/board_level_flash.html
* ROScube-Pico (system level): https://adlink-ros.github.io/roscube-doc/roscube-pico/flash_image/system_level_flash.html

Extend the storage
------------------

The default storage of NVIDIA SOM is not enough (especially for ROScube-Pico),
it's highly recommended to extend your storage with SD card / NVMe.

Please refer to `Mount rootfs on External Storage <https://adlink-ros.github.io/roscube-doc/roscube-pico/nvidia/advanced/mount_on_external_storage/index.html>`_ to extend your storage.

Install CUDA library
--------------------

Although we use the container, we still need to install the CUDA library on the native host.
Then share the CUDA library with the container.

.. code-block:: bash

    sudo apt update
    sudo apt install nvidia-cuda nvidia-l4t-cuda

Install Neuron Startup Menu
---------------------------

ADLINK provides the docker image with ROS/ROS2 environment inside.
You can use the image by installing Neuron Startup Menu.

.. code-block:: bash

    sh -c "MENU_CONFIG=ros_menu_20.04_container.yaml USE_CONTAINER=True $(curl -fsSL https://raw.githubusercontent.com/Adlink-ROS/ros_menu/main/scripts/setup.sh)"

Set the docker privilege

.. code-block:: bash

    sudo apt install docker.io
    sudo groupadd docker
    sudo gpasswd -a $USER docker
    sudo reboot

When you open a new terminal, it'll show which kind of envrionment you want to run.
For more information, refer to `Neuron Startup Menu <https://adlink-ros.github.io/roscube-doc/neuronsdk/neuron_startup_menu/installation.html>`_.

Install necessary packages in the container
-------------------------------------------

Since NVIDIA CUDA from Jetpack 4.6 has some limitation to run in Ubuntu 20.04 container,
we still need to do the following settings in your container.

.. code-block:: bash

    # CUDA 10.2 only supports gcc8 and g++8
    sudo apt update
    sudo apt install gcc-8 g++-8
    sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-8 8
    sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-8 8
    # Install libcudnn8-dev
    sudo apt install libcudnn8-dev

Run YOLO Object Detection example
---------------------------------

Now it works! You can try the `YOLO Object Detection example <https://adlink-ros.github.io/roscube-doc/roscube-pico/nvidia/packages/jetpack_sdk/jetpack_sdk_yolo.html>`_ now.
