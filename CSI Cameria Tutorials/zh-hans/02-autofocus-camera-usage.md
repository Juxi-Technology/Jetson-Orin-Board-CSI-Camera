[English](../en/02-autofocus-camera-usage.md) | [Deutsch](../de/02-autofocus-camera-usage.md) | [Español](../es/02-autofocus-camera-usage.md) | [Français](../fr/02-autofocus-camera-usage.md) | [Italiano](../it/02-autofocus-camera-usage.md) | [日本語](../ja/02-autofocus-camera-usage.md) | [한국어](../ko/02-autofocus-camera-usage.md) | [Português (BR)](../pt-br/02-autofocus-camera-usage.md) | [Português (PT)](../pt-pt/02-autofocus-camera-usage.md) | 简体中文 | [繁體中文](../zh-hant/02-autofocus-camera-usage.md)

# 02、自动对焦摄像头使用

## 1、查看video设备

```Plain Text
ls /dev/video*
```

图片的结果是接了两个CSI摄像头、一个USB摄像头的结果：一般一个CSI摄像头显示一个`video`设备，一个USB摄像头显示两个`video`设备，USB摄像头选择新增加且数字较小的`/dev/video2`调用（接上USB摄像头系统新增`/dev/video2`、`/dev/video3`设备号）

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

## 2、GUVCView

GUVCView是一个用于Linux系统的开源软件，用于捕捉和录制视频和图像，主要用于Webcam摄像头。

### 2\.1、GUVCView安装

```Plain Text
sudo apt update
sudo apt install guvcview -y
```

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

### 2\.2、GUVCView使用

进入应用菜单栏点击`guvcview`图标或者终端输入启动命令：选择USB摄像头，CSI摄像头无预览画面

```Plain Text
guvcview
```

![截图\_20250925170724\.png](../en/images/截图_20250925170724.png)

![Screenshot from 2025\-07\-30 17\-04\-00\.png](../en/images/Screenshot%20from%202025-07-30%2017-04-00.png)

## 3、VLC

VLC media player是一个自由且开源的多媒体播放器，支持多种音频和视频格式以及DVD、音频CD、VCD和各种流媒体协议。

### 3\.1、VLC安装

```Plain Text
sudo apt update
sudo apt install vlc -y
```

![Screenshot from 2025\-07\-30 17\-05\-31\.png](../en/images/Screenshot%20from%202025-07-30%2017-05-31.png)

### 3\.2、VLC使用

进入应用菜单栏点击`VLC media player`图标或者终端输入启动命令：选择USB摄像头，CSI摄像头无预览画面

```Plain Text
vlc
```

![Screenshot from 2025\-07\-30 17\-06\-32\.png](../en/images/Screenshot%20from%202025-07-30%2017-06-32.png)

![Screenshot from 2025\-07\-30 17\-07\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-07-09.png)

选择USB摄像头对应的设备号：

![截图\_20250925170820\.png](../en/images/截图_20250925170820.png)

![Screenshot from 2025\-07\-30 17\-08\-35\.png](../en/images/Screenshot%20from%202025-07-30%2017-08-35.png)



