开始训练
=============

以yolov10 or yolov8 为例 (`官方文档 <https://docs.ultralytics.com/quickstart/#conda-docker-image>`__ )
---------------------------------------------------------------------------------------------------------

.. note::
    * `yolov5可参考北极熊战队的教程 <https://flowus.cn/lihanchen/share/f9fb7cb0-5d7d-409c-8c4d-81ada554c598>`__


* 配置数据集

.. note::

    yolo系列模型支持coco或coco txt数据集标注格式

数据集目录结构应为

.. code-block:: none

    ├─dataset
        ├─test # test数据集可有可无
        │  ├─images
        │  └─labels
        ├─train
        │  ├─images
        │  └─labels
        └─valid
            ├─images
            └─labels

* 创建data.yaml,比如

.. code-block:: yaml

    # Train/val/test sets as 1) dir: path/to/imgs, 2) file: path/to/imgs.txt, or 3) list: [path/to/imgs1, path/to/imgs2, ..]

    path: dataset  # dataset root dir
    train: train/images  # train images (relative to 'path') 
    val: val/images  # val images (relative to 'path') 
    test:  # test images (optional)

    # Classes
    nc: 1
    names:
    0: car

* 创建训练脚本

.. code-block:: python

    if __name__ == '__main__':
        from ultralytics import YOLOv10
        model = YOLOv10(r'G:\yolov10\runs\detect\train2\weights\last.pt')
        model.train(data='data.yaml', epochs=100, batch=64, imgsz=480)

* 开始训练

在python控制台中输入

.. code-block:: python 

    import torch
    print(torch.cuda.is_available)

输出若为true则可以用显卡进行训练，若为false则转到常见问题查看解决方案.

* 创建预测脚本

.. code-block:: python

    from ultralytics import YOLOv10

    # Load a model
    model = YOLOv10(r"G:\yolov10\runs\detec.. note::t\train2\weights\best.pt")  # load a custom model
    source = r"your.mp4"  # predict on a video
    # results = model(source, stream=True)  # generator of Results objects
    results = model.predict(source, conf=0.6,device='0',half=False,imgsz=480,show=True)  # generator of Results objects

* `模型导出请看官方教程 <https://docs.ultralytics.com/modes/export/#arguments>`__


2024.9.2 123456dfg edit

.. contents:: Table of Contents
   :depth: 1
   :local: