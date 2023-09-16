.. _nlib_rosdriver:

ROS 2 drvier
############

For ROS 2 users, examples provided from ADLINK are available at the following link:
https://github.com/Adlink-ROS/neuron_library_example.git

.. note::

    These examples are only tested under ROS 2 foxy.

1. Install ROS.

2. Create a workspace and git clone the following package from github.

.. code-block:: bash

    # You can name your workspace.
    mkdir -p neuronlib_example_ws/src
    cd neuronlib_example_ws/src
    git clone https://github.com/Adlink-ROS/neuron_library_example.git
    cd ..

3. Build the ROS 2 package.

.. code-block:: bash

    colcon build --cmake-args -DCMAKE_BUILD_TYPE=Release

4. Source the package.

.. code-block:: bash

    #Source the package everytime you open a new terminal
    source install/local_setup.bash

5. Tutorials of the examples are provided at the links below.

* GPIO example: https://github.com/Adlink-ROS/neuron_library_example/tree/master/gpio_example
* I2C example: https://github.com/Adlink-ROS/neuron_library_example/tree/master/i2c_example
* LED example: https://github.com/Adlink-ROS/neuron_library_example/tree/master/led_example
* Serial example: https://github.com/Adlink-ROS/neuron_library_example/tree/master/serial_example
* PWM example: https://github.com/Adlink-ROS/neuron_library_example/tree/master/pwm_example
* SPI example: https://github.com/Adlink-ROS/neuron_library_example/tree/master/spi_example
