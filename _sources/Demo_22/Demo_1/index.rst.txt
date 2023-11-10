.. _cyclonedds:

Eclipse Cyclone DDS
===================

`Eclipse Cyclone DDS <https://github.com/eclipse-cyclonedds/cyclonedds>`_ is open-source DDS implementation,
which is contributed to Eclipse foundation by ADLINK initially.

Cyclone DDS is used by a growing list of `adopters <https://iot.eclipse.org/adopters/?#iot.cyclonedds>`_.
It's default DDS implementation of Autoware and tier-1 middleware of Robot Operating System (ROS 2).

For more information, refer to `the Cyclone DDS documentation <https://cyclonedds.io/docs/>`_.

Build
-----

To keep the development environment cleaner, you can use ``colcon`` to build Cyclone DDS.

* Get source code from GitHub

.. code:: bash

    mkdir -p ~/cyclonedds_ws/src
    cd ~/cyclonedds_ws/src
    git clone https://github.com/eclipse-cyclonedds/cyclonedds.git

* Build

.. code:: bash

    cd ~/cyclonedds_ws
    colcon build --cmake-args -DCMAKE_BUILD_TYPE=Release -DBUILD_EXAMPLES=ON

Example
-------

* Build example code

.. code:: bash

    cd ~/cyclonedds_ws
    source install/local_setup.bash
    cd ~/workspace/dds_ws/install/cyclonedds/share/CycloneDDS/examples/helloworld
    cmake -Bbuild -H. 
    cmake --build build

* Run example publisher

.. code:: bash

    cd ~/workspace/dds_ws/install/cyclonedds/share/CycloneDDS/examples/helloworld/build
    ./HelloworldPublisher

* Run example subscriber

.. code:: bash

    cd ~/workspace/dds_ws/install/cyclonedds/share/CycloneDDS/examples/helloworld/build
    ./HelloworldSubscriber
