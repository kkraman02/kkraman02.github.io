.. _nlib_usage:

Usage
#####

API
---

Neuron Library provides two kinds of API: 

* C: http://iotdk.intel.com/docs/master/mraa/
* Python3: http://iotdk.intel.com/docs/master/mraa/python/

Pin Mapping
-----------

This library is developed for ADLINK products.
Supported hardware and information about the ROSCube I/O pin mapping can be found at: https://github.com/Adlink-ROS/mraa#supported-hardware.

C Example
---------

1. Install necessary packages.

.. code-block:: bash

    sudo apt install build-essential cmake

2. Create a working space under the ``/home`` directory and navigate to it.

.. code-block:: bash

    mkdir neuronlibex_ws
    cd neuronlibex_ws

3. Copy the example file to your working space.

.. code-block:: bash

    cp -r /opt/adlink/neuron-sdk/neuron-library/share/mraa/* .

4. Create a "build" directory under your working space and navigate to it.

.. code-block:: bash

    mkdir build
    cd build

5. Build the examples.

.. code-block:: bash

    cmake ../examples/
    make

6. Run the examples under the directory ``~/neuronlibex_ws/build/c/``.

.. code-block:: bash

    cd c/
    ./<the example you want to execute>

.. note:: 

    Refer to `C Examples <https://github.com/Adlink-ROS/mraa/blob/roscube_series/examples/c/README.md>`_ for more usage

Python Example
--------------

1. Create a working space under the ``/home`` directory and navigate to it.

.. code-block:: bash

    mkdir neuronlibex_ws
    cd neuronlibex_ws

2. Copy the example file to your working space.

.. code-block:: bash

    cp -r /opt/adlink/neuron-sdk/neuron-library/share/mraa/* .

3. Move into the directory with the python examples.

.. code-block:: bash

    cd examples/python/

4. Run the python3 examples:

.. code-block:: bash

    python3 <the example you want to execute>.py

.. note:: 

    Refer to `Python Examples <https://github.com/Adlink-ROS/mraa/blob/roscube_series/examples/python/README.md>`_ for more usage
