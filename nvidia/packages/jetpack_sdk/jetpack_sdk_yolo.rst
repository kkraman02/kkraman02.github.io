YOLO Object Detection
#####################

1. Set up your environment.
---------------------------

.. code-block:: bash

    export CUDA_HOME=/usr/local/cuda
    export PATH=$CUDA_HOME/bin:$PATH
    export LD_LIBRARY_PATH=$CUDA_HOME/lib64:$LD_LIBRARY_PATH

.. note::
    You can also add path to ``.bashrc``.

2. Check nvcc is workable.
--------------------------

.. code-block:: bash

    nvcc --version

.. image:: images/nvcc.png
  :width: 80%
  :align: center

3. Retrive darknet repository from github.
------------------------------------------

.. code-block:: bash

    sudo apt update
    sudo apt install git
    git clone https://github.com/AlexeyAB/darknet.git

4. Build darknet with CUDNN and OpenCV support.
-----------------------------------------------
Modify darknet's Makefile with the following:

    * GPU=1
    * CUDNN=1
    * OPENCV=1

.. code-block:: bash

    sudo apt update
    sudo apt install make build-essential
    cd darknet
    # Edit Makefile GPU=1, CUDNN=1, OPENCV=1
    make

5. Download the pre-trained weights.
------------------------------------

.. code-block:: bash

    wget https://pjreddie.com/media/files/yolov3-tiny.weights

.. note::

    ADLINK doesn't own the pre-trained data.
    This pre-trained data is a contribution from original author in community.

6. Run object detector from example image.
------------------------------------------

.. code-block:: bash

    ./darknet detect cfg/yolov3-tiny.cfg yolov3-tiny.weights data/dog.jpg

.. image:: images/run-yolo.png
  :width: 80%
  :align: center

.. image:: images/predictions.jpg
  :width: 80%
  :align: center
