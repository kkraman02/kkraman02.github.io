.. _nmenu_usage:

Usage
#####

Options
-------

After installation, there is a menu everytime you open the terminal.

.. image:: images/menu_option.png
  :width: 80%
  :align: center

* Do nothing: Do not load any environment.
* ROS 1 noetic: Load ROS 1 noetic environment.
* ROS 2 foxy: Load ROS 2 foxy environment.
* ROS2/ROS1_bridge: Load ROS bridge environment and run ROS bridge automatically.
* Help: Show the usage of ROS menu.

.. note:: 
    
    While using container, the docker image will be pulled at the first time running ROS environment.


Useful Commands
---------------

* ``ros_menu_disable``: Disable the ROS menu while opening a new terminal.
* ``ros_menu_enable``: Enable the ROS menu while opening a new terminal.
* ``ros_menu_env``: Show the environmental variables of current shell.
* ``ros_menu_clean_docker``: Clean docker image & container. Note that the packages you install in the container before will be lost.

Configuration
-------------

The configuration of the Menu is ``~/.ros_menu/config.yaml``.
You can refer to the `README <https://github.com/Adlink-ROS/ros_menu>`_ for more information.
