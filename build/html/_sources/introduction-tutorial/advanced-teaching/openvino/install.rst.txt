openvino的安装
==================


* `官方教程(英文好的建议直接看) <https://docs.openvino.ai/2024/get-started/install-openvino/install-openvino-archive-windows.html>`
  
非官方中文教程
----------------------

* 下载并安装 OpenVINO 核心组件

.. code-block:: bash

    sudo mkdir /opt/intel
    cd <user_home>/Downloads
    curl -L https://storage.openvinotoolkit.org/repositories/openvino/packages/2024.3/linux/l_openvino_toolkit_ubuntu22_2024.3.0.16041.1e3b88e4e3f_x86_64.tgz --output openvino_2024.3.0.tgz
    tar -xf openvino_2024.3.0.tgz
    sudo mv l_openvino_toolkit_ubuntu22_2024.3.0.16041.1e3b88e4e3f_x86_64 /opt/intel/openvino_2024.3.0
    cd /opt/intel/openvino_2024.3.0
    sudo -E ./install_dependencies/install_openvino_dependencies.sh
    cd /opt/intel/openvino_2024.3.0 
    python3 -m pip install -r ./python/requirements.txt
    cd /opt/intel
    sudo ln -s openvino_2024.3.0 openvino_2024
    echo "source /opt/intel/openvino_2024/setupvars.sh" >> ~/.bashrc
    source ~/.bashrc

* 验证是否安装成功

.. code-block:: bash
    
    cd /opt/intel/openvino_2024/deployment_tools/demo
    ./demo_squeezenet_download_convert_run.sh


2024.9.2 123456dfg edit

.. contents:: Table of Contents
   :depth: 3
   :local:


