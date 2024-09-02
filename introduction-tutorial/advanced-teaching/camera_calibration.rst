相机标定
===========

ROS2 camera_calibration
-------------------------

* 安装(非常简单)

.. code-block:: bash

    sudo apt install ros-humble-camera-calibration -y

* 使用

.. note:: 

    使用前记得先启动相机节点

.. code-block:: bash

    ros2 run camera_calibration cameracalibrator --size 8x11 --square 0.02 image:=/image_raw camera:=/my_camera


2024.9.2 123456dfg edit



.. contents:: Table of Contents
   :depth: 4
   :local: