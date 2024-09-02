模型的使用
=================


使用OpenVino将onnx模型转换成ir模型(python)
--------------------------------------------

* `官方文档 <https://docs.openvino.ai/2024/openvino-workflow/model-preparation/convert-model-onnx.html>`__

.. code-block:: python

   import openvino as ov
   ov.convert_model('your_model_file.onnx')

使用OpenVino将pt模型转换成ir模型(python)
----------------------------------------


* `官方文档 <https://docs.openvino.ai/2024/openvino-workflow/model-preparation/convert-model-pytorch.html>`__

.. code-block:: python

   import torchvision
   import torch
   import openvino as ov
   model = torchvision.models.resnet50(weights='DEFAULT')
   ov_model = ov.convert_model(model)


.. contents:: Table of Contents
   :depth: 3
   :local: