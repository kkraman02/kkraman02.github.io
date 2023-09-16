How to Use AI Benchmark
#######################

The tutorial will guide you how to use AI Benchmark on ROScube series.

Introduction
^^^^^^^^^^^^

We used **AI Benchmark** to evaluate GPU performance on ROScube series.

`AI Benchmark Alpha <https://ai-benchmark.com/alpha.html>`_ is an open source python library for evaluating AI performance of various hardware platforms, including CPUs, GPUs and TPUs.

Usage
^^^^^

Here, we provided two usages on different ROScube series.

.. note:: 
    
    | GPU with at least 2GB of RAM is required for running inference tests / 4GB of RAM for training tests.
    | The benchmark is compatible with both TensorFlow 1.x and 2.x versions. 

ROScube-X series and ROScube-Pico series:
-----------------------------------------

1. Install `Jetpack <https://docs.nvidia.com/jetson/jetpack/install-jetpack/index.html>`_

2. Install `Tensorflow <https://docs.nvidia.com/deeplearning/frameworks/install-tf-jetson-platform/index.html>`_

3. Install `ai-benchmark <https://pypi.org/project/ai-benchmark/>`_  by terminal command
   
.. code-block:: bash
    
    pip install ai-benchmark

4. Use the following python code to run the benchmark:

.. code-block:: bash

    from ai_benchmark import AIBenchmark  
    results = AIBenchmark().run()

To run inference or training only, use ``benchmark.run_inference()`` or ``benchmark.run_training()``. 

ROScube-I series:
-----------------

Requirement:

   * Python: 3.8
   * Keras: 2.6
   * TensorFlow: 2.6
   * Cuda: 11.4
   * CudNN: 8.2
   * Nvidia-driver: >= 470

1. Install `GPU Driver <https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html#installdriver>`_

2. Download CUDA from `Nvidia website <https://developer.nvidia.com/cuda-downloads>`_.

3. `Download <https://developer.nvidia.com/cudnn>`_ and `install <https://docs.nvidia.com/deeplearning/sdk/cudnn-install/index.html>`_ cuDNN.
   
4. Install Tensorflow by terminal command:

.. code-block:: bash

    pip install tensorflow==<version>

5. Install `ai-benchmark <https://pypi.org/project/ai-benchmark/>`_ by terminal command:

.. code-block:: bash

    pip install ai-benchmark

6. Use the following python code to run the benchmark:

.. code-block:: bash

    from ai_benchmark import AIBenchmark  
    results = AIBenchmark().run()

To run inference or training only, use ``benchmark.run_inference()`` or ``benchmark.run_training()``. 

Results
^^^^^^^

In total, AI Benchmark consists of 42 tests and 19 sections.

After testing, you will get the Score of GPU performance:

    * Inference Score
    * Training Score
    * AI Score

Then go to the `ranking page <https://ai-benchmark.com/ranking_deeplearning.html>`_, and you can compare your device with open data.

And, we provided some testing data of ROScube:

.. toctree::
   :maxdepth: 1

   ai_benchmark_result.rst

Common Issue
^^^^^^^^^^^^

When you run the python code, but you can't show the CUDA version, like N/A.

1. Make sure install CUDA, you can find it in ``/usr/local/cuda*``
2. Gedit ``.bashrc`` by terminal command:
   
.. code-block:: bash

    gedit ~/.bashrc

3. Add the CUDA's path to ``./bashrc``

.. code-block:: bash 
    
    export PATH=/usr/local/cuda/bin:$PATH
    export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH

4. Refresh and check CUDA

.. code-block:: bash
    
    source ~/.bashrc
    nvcc -V