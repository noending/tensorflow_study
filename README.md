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
然后在Jupyter中运行，就能得到被标示的结果了：
![](https://github.com/noending/tensorflow_study/blob/master/images/download-1.png)

### [tf图片视频检测.ipynb](https://github.com/noending/tensorflow_study/blob/master/tf%E5%9B%BE%E7%89%87%E8%A7%86%E9%A2%91%E6%A3%80%E6%B5%8B.ipynb)

添加了SSD视频实时检测功能

### [tf-object_detection API训练验证的及可视化流程.txt](https://github.com/noending/tensorflow_study/blob/master/tf%20object_detection%20API%E8%AE%AD%E7%BB%83%E9%AA%8C%E8%AF%81%E7%9A%84%E5%8F%8A%E5%8F%AF%E8%A7%86%E5%8C%96%E6%B5%81%E7%A8%8B.txt)

Tensorflow detection API从训练到评估以及tensorboard可视化
