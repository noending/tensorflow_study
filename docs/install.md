# 安装

依赖
---
Tensorflow 物体检测API需要以下库
---
* Protobuf 3+
* Python-tk
* Pillow 1.0
* lxml
* tf Slim (which is included in the "tensorflow/models/research/" checkout)
* Jupyter notebook
* Matplotlib
* Tensorflow(推荐1.4以上）
* Cython
* cocoapi

对于Tensorflow的具体安装可以根据[官网指示](https://www.tensorflow.org/install/)，也可以用以下命令：
```
# For CPU
pip install tensorflow
# For GPU
pip install tensorflow-gpu
```
ps. tensorflow 在mac上1.2之后就不支持gpu了

剩下的库在Ubuntu16.04上可以用apt-get：
```
sudo apt-get install protobuf-compiler python-pil python-lxml python-tk
sudo pip install Cython
sudo pip install jupyter
sudo pip install matplotlib
```

另外也可以用pip安装依赖：
```
sudo pip install Cython
sudo pip install pillow
sudo pip install lxml
sudo pip install jupyter
sudo pip install matplotlib
```
对用mac用户，推荐用conda， conda install 以上的库

### COCO API 安装：
---
[COCO](https://github.com/cocodataset/cocoapi)是一个大型图片数据集，用来检测物体，分割和人物关键点等识别，安装之前，需要做的是：

* git clone tensorflow的models,或者直接下载
```
git clone https://github.com/tensorflow/models.git
``` 
通过以下命令，copy pycocotools到models的research的文件夹
```
git clone https://github.com/cocodataset/cocoapi.git
cd cocoapi/PythonAPI
make
cp -r pycocotools <path_to_tensorflow>/models/research/
```
如果你喜欢用COCO的评估评估指标，添加```metrics_set: "coco_detection_metrics"```到config文件夹中的```eval_config```.如果要用COCO的实例切割指标添加```metrics_set: "coco_mask_metrics"```到同样的文件中

---

### Protobuf 编译
---
由于tf目标检测API用的是Protobufs来配置模型和训练参数，所以在用框架之前，必须编译Protobuf的库，可以在tensorflow/models/research/文件夹路径下运行命令：
```
# From tensorflow/models/research/
protoc object_detection/protos/*.proto --python_out=.
```

### 添加库到python路径下 PYTHONPATH：

本地运行时，tensorflow/models/research/ 和slim的文件夹应该依附到PYTHONPATH，可以在tensorflow/models/research/路径下运行命令：
```
# From tensorflow/models/research/
export PYTHONPATH=$PYTHONPATH:`pwd`:`pwd`/slim
```
ps. 这个命令每次都要重新运行，当你用开始新的terminal终端时，可以添加到~/.bashrc文件夹中或者～/.zshrc如果你用ohzsh的话

### 最后测试安装
---
检测tf目标检测API所依赖的库是否都正确安装，通过以下命令：

```python object_detection/builders/model_builder_test.py``` 