# [Tensorflow 目标检测API](https://github.com/tensorflow/models/tree/master/research/object_detection)

在计算机视觉领域中建立一个在一张图片中能精准定位和识别多物体的机器学习模型还是一个巨大的挑战.所以现在不得不介绍Tesnsorflow目标检测API，这是一个建立在tf之上的开源框架，它很容易创建,训练和部署物体目标检测模型.

![](https://github.com/noending/tensorflow_study/blob/master/images/kites_detections_output.jpg)

---
### 使用说明

* [安装](https://github.com/noending/tensorflow_study/blob/master/docs/install.md)

---
如果你成功安装以上安装就可以打开[object_detection_tutorial.ipynb](https://github.com/noending/tensorflow_study/blob/master/object_detection_tutorial.ipynb),在此说明在第三个下载模型的块，会出错，一直time out，推荐在http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17.tar.gz 下载.
并注释这两行：
```
#opener = urllib.request.URLopener()
#opener.retrieve(DOWNLOAD_BASE + MODEL_FILE, MODEL_FILE)
```
