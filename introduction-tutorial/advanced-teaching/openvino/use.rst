openvino的使用
===============

在python环境下使用
--------------------------

.. code-block:: python

    import openvino as ov

在c++环境中使用

* cmakelist.txt配置
  
.. code-block:: cmake

    find_package(OpenVINO REQUIRED COMPONENTS Runtime ONNX)
    include_directories(
        #OpenVINO推理引擎的头文件
        /opt/intel/openvino_2024/runtime/include/ie/
        /opt/intel/openvino_2024/runtime/include/ngraph/
        /opt/intel/openvino_2024/runtime/include/openvino/
    )
    target_link_libraries(
        ${PROJECT_NAME}
        /opt/intel/openvino_2024/runtime/lib/intel64/libopenvino.so
        openvino::frontend::onnx openvino::runtime
    )

* c++头文件引入

.. code-block:: c++

    #include <openvino/openvino.hpp>


* `openvino官方例子<https://docs.openvino.ai/nightly/learn-openvino/openvino-samples/hello-classification.html>`



2024.9.2 123456dfg edit

.. contents:: Table of Contents
   :depth: 3
   :local:
