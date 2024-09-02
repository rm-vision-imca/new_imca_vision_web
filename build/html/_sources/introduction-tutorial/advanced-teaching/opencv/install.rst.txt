OpenCV的安装
==================

.. note::

    本教程的安装环境在Ubuntu22.04，本人不建议在windows上配置安装OpenCV。
    一般直接安装ros2二进制文件会自带OpenCV库

从apt源中安装
-------------------

.. code-block:: bash

    sudo apt update && sudo apt upgrade -y
    sudo apt-get install libopencv-dev python3-opencv -y

从源代码中安装
-----------------------

.. code-block:: bash

    sudo apt-get install build-essential cmake git pkg-config libgtk-3-dev libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev libjpeg-dev libpng-dev libtiff-dev gfortran openexr libatlas-base-dev python3-dev python3-numpy libtbb2 libtbb-dev -y
    cd ~/
    git clone https://github.com/opencv/opencv.git
    git clone https://github.com/opencv/opencv_contrib.git
    cd opencv
    mkdir build && cd build
    cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D INSTALL_C_EXAMPLES=ON -D INSTALL_PYTHON_EXAMPLES=ON -D OPENCV_GENERATE_PKGCONFIG=ON -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules -D BUILD_EXAMPLES=ON ..
    make -j
    sudo make install

验证是否安装成功
------------------------

.. code-block:: bash

    pkg-config --modversion opencv4

* 您应该得到以下输出：
  
.. code-block:: none

    4.6.0 # 或者其他有效版本号

* 您还可以使用以下命令检查 OpenCV 模块的版本(python3 api):
  
.. code-block:: bash

    python3 -c "import cv2; print(cv2.__version__)"

* 您应该得到以下输出：

.. code-block:: none

    4.2.0-dev # 或者其他有效版本号



2024.9.2 123456dfg edit


.. contents:: Table of Contents
   :depth: 1
   :local:






