

# TrafficSignsRecognition

基于android断的限速牌识别,并且实时地报出限速数字,并且只报一次

程序使用android studio开发,使用的语言是java和c++混合编程的

程序使用说明:
1.安装OpenCV_3.1.0_Manager_3.10_armeabi-v7a.apk
2.在手机本地存储目录下中建立caffe_mobile/traffic-signs文件夹
3.将安装里面的cnn里面的全部文件复制到caffe_mobile/traffic-signs文件夹中
4.安装app-debug.apk。

先点下opencv manager
再点击这个程序。
进入程序后，点击实时运行。
将相机对准视屏屏幕，即可。


若未出现相机，需在手机设置中设置权限，需给摄像头权限和存储权限。


说明:
程序分为两步:
1.检测
1.1 用adaboost进行的圆形形状训练，训练参数保存在circle.xml中，使用这个参数和adaboost进行图像检测。
1.2 将检测到的小图像转换到hsv和hiv,进行红色和蓝色的颜色判别
1.3 用ANN_MLP判别是否是标志牌

2.识别
用卷积神经网络进行识别
网络共5层，具体见cnn里面的config_deploy.prototxt。2层卷几层,3层全连接层,最后softmax
将标志牌分为了34类，前12类为限速牌。
训练样本为GTSRB的部分数据。
在电脑上测试识别率为96%左右。


程序可设置一些参数
圆形尺寸为检测的大小范围
颜色阈值为颜色判断时用到的，越大颜色判断越严
重复判断为识别输出结果的最后识别到几次才输出，和发语音
间隔时间为隔多少时间发声音

手机端识别率会低很多
原因:
1. 是对屏幕放的视频进行识别，屏幕分辨率不高，太模糊
2. 光线影响
3. 手机手拿拿着太晃，容易造成图像模糊，导致识别错误。

效果视频

[限速牌识别](http://v.youku.com/v_show/id_XMzQ3MTM1MTU0MA==.html?spm=a2hzp.8244740.0.0)


效果图

![avatar](1.png)	
![avatar](2.png)
![avatar](3.png)
![avatar](4.png)
![avatar](5.png)
