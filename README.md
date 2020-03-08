# helmet_detection_yolov3
detect persons with/without helmets using YOLOv3(使用YOLOv3检测是否戴头盔)

## 准备
- 训练数据集：https://github.com/njvisionpower/Safety-Helmet-Wearing-Dataset
- Pascal VOC格式转YOLO格式工具：https://github.com/ssaru/convert2Yolo
- 检测模型：YOLOv3 https://github.com/AlexeyAB/darknet
- 训练平台：Colab

注：
1. 原始训练数据集中标注格式为xml，而YOLO的标注格式为txt，因此需要进行转换，上面的转换工具在进行转换时存在bug，详见https://blog.csdn.net/MacwinWin/article/details/104486726 可以使用我修改过的代码：https://github.com/MacwinWin/convert2Yolo/tree/fixed

2. 原始训练数据集中存在错误标注，转换中会报错，嫌麻烦的话可以使用我修改过的数据集https://drive.google.com/file/d/1JAnspVqYeRRlJZ2mfD2uzC_E14652T4S/view?usp=sharing

3. Colab训练YOLO需要几个小trick，具体可以去搜一下，我近期也会进行总结。

## 训练
由于没有写论文的需要（主要还是因为是懒），我把原始数据集中的训练集、验证集、测试集全部合并为训练集，进行训练，训练参数全部使用默认的参数

## 效果
由于使用Colab，训练过程不连续，故没有形成一张完整的loss图，记得大概是在20000步左右loss下降就很不明显了，到最后基本维持在2.3左右。在39000步后我停止训练并保存参数文件。在一个网络视频上进行测试，效果如下：
<p align="center"> 
<img src="https://github.com/MacwinWin/helmet_detection_yolov3/blob/master/result.gif" width = 100% height = 100%>
</p> 
出乎我意料的的是，视频结尾那个几乎小到只有几十个像素点的头像也被检测出来了。。。

感兴趣的可以使用我训练结果再接着训练：[Google Drive](https://drive.google.com/file/d/1-799sXS3wHe7HjwSborwSf1WemuYH_RL/view?usp=sharing)
