#easydarwin-forward
海康摄像头实时视频流媒体转发，直接转发海康RTSP流媒体。需要知道需要转发的海康摄像头的IP地址、登录账户以及密码。

注：本示例为windows平台下

##启动服务：
打开CMD窗口并跳转到 easydarwin 文件目录下，通过如下命令来启动服务
```
easydarwin -d -c easydarwin.xml
```

##RTSP配置
找到目录下的 devices.xml 文件，进行RTSP实时流媒体配置。
```
<?xml version="1.0" encoding="GB2312"?>
<Devices>
	<Device id="0" name="demo_1" url="rtsp://username:password@ip/h264/ch1/sub/av_stream"/>
    <Device id="1" name="demo_2" url="rtsp://username:password@ip/h264/ch1/main/av_stream"/>
</Devices>
```
其中每一个< Device >为需要进行转发的RTSP流媒体配置

id：一个不重复的编号

name：该流媒体转发后的名称，后续通过该名称进行播放

url 属性说明:

username：登录摄像头的账户

password：登录摄像头的密码

ip：摄像头的ip地址

sub：表示海康视频流的子码流输出，不是很清晰

main：表示海康视频流的主码流输出，清晰


##转发播放
选择一个可以播放RTSP视频流的播放软件，一般推荐使用 VLC media player 播放器进行播放。
播放的流媒体地址为：
```
rtsp://easydarwin服务器ip:8554/name
```
easydarwin 服务默认使用 8554 端口。
