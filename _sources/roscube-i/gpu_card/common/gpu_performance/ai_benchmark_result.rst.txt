AI Benchmark Results
####################

Here we show the data and performance of GPUs by **AI-Benchmark** on **ROScube series**.

GPU Burn in / Test by `AI-Benchmark <https://ai-benchmark.com/alpha.html>`_.
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

AI Benchmark Alpha is an open source python library for evaluating AI performance of various hardware platforms, including CPUs, GPUs and TPUs.

It can be downloaded to any system running Windows, Linux or macOS.

In total, AI Benchmark consists of 42 tests and 19 sections provided below:

    * MobileNet-V2  [classification]
    * Inception-V3  [classification]
    * Inception-V4  [classification]
    * Inception-ResNet-V2  [classification]
    * ResNet-V2-50  [classification]
    * ResNet-V2-152  [classification]
    * VGG-16  [classification]
    * SRCNN 9-5-5  [image-to-image mapping]
    * VGG-19  [image-to-image mapping]
    * ResNet-SRGAN  [image-to-image mapping]
    * ResNet-DPED  [image-to-image mapping]
    * U-Net  [image-to-image mapping]
    * Nvidia-SPADE  [image-to-image mapping]
    * ICNet  [image segmentation]
    * PSPNet  [image segmentation]
    * DeepLab  [image segmentation]
    * Pixel-RNN  [inpainting]
    * LSTM  [sentence sentiment analysis]
    * GNMT  [text translation]

| In the testing, we can get the training time of different models.
| Then AI-Benchmark will provide the score which the performance of GPUs. 

GPU Score
^^^^^^^^^

| After testing, we can go the `RANK <https://ai-benchmark.com/ranking_cpus_and_gpus.html>`_ to compare the performance of GPUs.

| In the rank, you can see the open testing data of different GPUs.  
| It is a fairer way to evaluate the performance of GPUs.

Here, we provided some test data of GPUs which we actual tested on **ROScube series**.

+----------------+---------------------+-----------------+----------------+---------+
|Device          |GPU                  |Inference Score  |Training Score  |AI Score |
+================+=====================+=================+================+=========+
|ROScube-I-E     |NVIDIA RTX A2000 12G |8530             |8915            |17445    |
+----------------+---------------------+-----------------+----------------+---------+
|ROScube-I-E     |NVIDIA GTX 1050  2G  |3200             |X               |X        |
+----------------+---------------------+-----------------+----------------+---------+
|ROScube-X-580   |Jetson AGX Xavier    |2142             |2192            |4334     |
+----------------+---------------------+-----------------+----------------+---------+
|ROScube-Pico-NX |Jetson Xavier NX     |709              |787             |1496     |
+----------------+---------------------+-----------------+----------------+---------+


.. note:: 

    GPU with at least **2GB** of RAM is required for running inference tests / **4GB** of RAM for training tests.
    
    The benchmark is compatible with both TensorFlow 1.x and 2.x versions. 