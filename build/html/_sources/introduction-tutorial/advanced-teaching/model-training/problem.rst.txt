常见问题
========

torch.cuda.is_available返回false
------------------------------------

* 检查pip或者conda安装的pytorch是否为cuda版本

.. code-block:: bash

    conda list #查看conda安装的软件包
    pip list #查看pip安装的软件包

找到torch 查看版本号是否为cuda版本，若不是则需要卸载重新到 `pytorch官网 <https://pytorch.org/get-started/locally/>`__ 内安装

* 卸载方法

.. code-block:: bash

    pip uninstall torch torchvision torchaudio # pip
    conda uninstall torch torchvision torchaudio # conda


显存不足报错
---------------

* 考虑迁移到服务器上进行训练

* 将训练脚本的batch调小，一般为2的倍数

分页文件过小报错
-------------------

* 到windows高级设置中，将虚拟内存调大，yolo系列一般50g以上分页大小可以满足



2024.9.2 123456dfg edit

.. contents:: Table of Contents
   :depth: 1
   :local: