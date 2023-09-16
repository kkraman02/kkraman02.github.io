How to use CAN bus
##################

The tutorial will guide you how to use CAN bus on NVIDIA Platform.

Supported Model: 

    * ROScube-X series
    * ROScube-Pico-NX series


Hardware Pinout
---------------

* For ROScube-X series

.. image:: images/pinout-x.png
  :width: 50%
  :align: center

* For ROScube-Pico-NX series

.. image:: images/pinout-pico.png
  :width: 50%
  :align: center

Configuration
-------------

1. Install necessary packages

.. code-block:: bash

    sudo apt update
    sudo apt install iproute2 can-utils

2. Configure the bitrate for can0

.. code-block:: bash

    sudo ip link set can0 type can bitrate 1000000

In this command, **bitrate** can be any valid CAN bitrate for stand CAN.

.. note:: 

    | 125000(125 Kbps), 250000(250 Kbps), 500000(500 Kbps) and 1000000(1Mbps) are supported bitrates for Tegra MTTCAN driver.
    | Any other bitrate is not validated on Tegra MTTCAN driver.

If you want to show more configuration usage:

.. code-block:: bash

    ip link set can0 type can help
 
3. Turn on can0

.. code-block:: bash

    sudo ip link set can0 up

4. Enter ``ifconfig``, then you should see can0

.. image:: images/ifconfig.png
  :width: 50%
  :align: center

Test
----

1. Connect CAN_H and CAN_L to other machines.

2. To receive CAN bus data from can0:

.. code-block:: bash

    candump can0 -t A

3. To send CAN bus data out of can0:

.. code-block:: bash

    cansend can0 123#1122334455667788

Loopback Test
-------------

If you just want to self-test the CAN function:

1. Turn loopback on:

.. code-block:: bash

    sudo ip link set can0 down
    sudo ip link set can0 type can loopback on
    sudo ip link set can0 type can bitrate 1000000
    sudo ip link set can0 up

2. To receive CAN bus data from can0:

.. code-block:: bash

    candump can0 -t A

3. To send CAN bus data out of can0:

.. code-block:: bash

    cansend can0 123#1122334455667788

4. Remember to turn loopback off

.. code-block:: bash

    sudo ip link set can0 down
    sudo ip link set can0 type can loopback off
    sudo ip link set can0 type can bitrate 1000000
    sudo ip link set can0 up
