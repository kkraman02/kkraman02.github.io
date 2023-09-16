Flash System Image to Target Machine
####################################

Once you prepared rootfs in step: *customize rootfs*. You can use flash.sh tool to flash image to target machine.

.. note:: 

    Remember to put machine into **recovery mode** before flashing.

.. code-block:: bash
    
    cd <driver package>
    # Put machine into recovery mode first.
    sudo ./flash.sh <target name> mmcblk0p1

+--------------------+-----------------------+
|Model               |Target Name            |
+====================+=======================+
|RQX-590             |jetson-agx-orin-rqx59x |
+--------------------+-----------------------+
|RQX-580             |rqx_580                |
+--------------------+-----------------------+
|RQX-58G             |rqx_58g                |
+--------------------+-----------------------+
|NPN-1 (Pico Nano)   |npn1                   |
+--------------------+-----------------------+
|NPN-2 (Pico AGX NX) |npn2                   | 
+--------------------+-----------------------+

.. note:: 

    The flashing procedure might take 8 ~ 10 minutes.