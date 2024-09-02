模型训练环境搭建
=====================

.. note:: 

    本教程在windows上进行,且使用nvidia独立显卡进行训练

conda环境安装
----------------------

* `下载Anaconda <https://www.anaconda.com/download#>`__

* 安装

* 使用anaconda prompt换源(清华大学源) 

.. code-block:: bash

    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge 
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
    conda config --set show_channel_urls yes

* 直接更换源文件

1.打开 ``anaconda prompt`` 创建源文件

.. code-block:: bash

    conda config --set show_channel_urls yes

2.找到 ``.condarc文件`` ，一般该文件在目录 ``C:\Users\用户名`` 路径下

3.以记事本打开 ``.condarc``，修改内容为

.. code-block:: none

    channels:
      - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
      - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/menpo/
      - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
      - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
      - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
      - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
      - https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
      - defaults
    show_channel_urls: true

4. 打开 ``anaconda prompt`` 清理缓存

.. code-block:: bash

    conda clean -i

5. 运行 ``conda config --show`` 查看是否换源成功


cuda,Cudnn环境安装(`详情见csdn <https://blog.csdn.net/YYDS_WV/article/details/137825313>`__)
------------------------------------------------------------------------------------------------


* 确定显卡支持的CUDA版本

在命令行里输入 ``nvidia-smi.exe``
找到cuda version 确定显卡支持的CUDA版本

.. note:: 
    如果输入无效或者未找到该程序，请检查是否正确安装显卡驱动。

自行搜索并安装对应版本的cuda

* 安装cudnn

1. 解压cudnn压缩包;

2. 找到cuda的安装目录，一般为NVIDIA Computing Toolkit\CUDA\v12.2;

3. 将CUDNN对应bin、lib、include三个文件与CUDA对应的bin、lib、include进行合并，将CUDNN内文件全部复制到CUDA对应文件夹内;
   
4. 添加环境变量: 在“系统变量”中Path添加NVIDIA Computing Toolkit\CUDA\v12.2\lib和v12.2\libnvvp以及v12.2\include ;
   
5. 检查CUDNN是否安装成功:找到NVIDIA Computing Toolkit\CUDA\v12.2\extras\demo_suite，查看是否有文件bandwidthTest.exe以及deviceQuery.exe，若存在则在该文件中打开cmd运行两.exe文件,运行成功应有表格显示。




pytorch安装
------------------

* `官方文档 <https://pytorch.org/get-started/locally/>`__

* 从conda安装

选择对应cuda版本的pytorch进行安装，如:

.. code-block:: bash

    conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia

* 从pip安装

.. note::

    从pip安装要在对应的conda虚拟环境中进行，否则将会装到系统默认的全局python解释器中，无法正常使用

.. code-block:: bash

    pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118





2024.9.2 123456dfg edit

.. contents:: Table of Contents
   :depth: 1
   :local: