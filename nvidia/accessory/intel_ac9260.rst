:orphan:

Using Intel AC9260 WiFi Card
############################

The tutorial will guide you how to use Intel AC9260 on ROScube.

1. Install the WiFi Card into ROScube

2. Install ``add-apt-repository``

.. code-block:: bash

    sudo apt install software-properties-common

3. Install Canonical backport driver

.. code-block:: bash

    sudo add-apt-repository ppa:canonical-hwe-team/backport-iwlwifi
    sudo apt-get update
    sudo apt install backport-iwlwifi-dkms

4. Reboot the system and you can use Intel AC9260 now.
