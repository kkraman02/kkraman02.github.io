.. _nmenu_installation:

Installation
############

Install
-------

While installing Neuron Startup Menu, it'll also setup the ROS environment.
You can choose whether to install ROS environment in native host or in container.

* Native Host

.. code-block:: bash
    
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/Adlink-ROS/ros_menu/master/scripts/setup.sh)"

* Container (Suggested in NVIDA platform)

.. code-block:: bash

    sh -c "MENU_CONFIG=ros_menu_20.04_container.yaml USE_CONTAINER=True $(curl -fsSL https://raw.githubusercontent.com/Adlink-ROS/ros_menu/main/scripts/setup.sh)"

* Add docker privilege to the current user (Only needed if you install ROS environment in container) 

.. code-block:: bash

    sudo apt install docker.io
    sudo groupadd docker
    sudo gpasswd -a $USER docker
    sudo reboot

.. note:: 
    
    If you use NVIDA series platform (e.g. ROScube-X / ROScube Pico), suggest to **install ROS environment in container**.
    Since NVIDIA platform BSP is Ubuntu 18.04, it's inconvenient to run ROS 2 foxy, which is the ROS LTS version.
    Open Robotics only supports ROS 2 foxy on Ubuntu 20.04.

.. warning::

    Since installing container needs extra disk space, make sure the remaining space is more than 5G.

.. note::

    We use Dockerfile to create the container image. The Dockerfile is from `this GitHub repository <https://github.com/Adlink-ROS/docker_image_creator>`_.

Uninstall
---------

If you don't want the Menu anymore, open the terminal and run ``ros_menu_uninstall`` and the Menu will be removed.
