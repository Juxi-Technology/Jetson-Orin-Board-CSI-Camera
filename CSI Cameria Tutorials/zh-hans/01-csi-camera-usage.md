[English](../en/01-csi-camera-usage.md) | [Deutsch](../de/01-csi-camera-usage.md) | [Español](../es/01-csi-camera-usage.md) | [Français](../fr/01-csi-camera-usage.md) | [Italiano](../it/01-csi-camera-usage.md) | [日本語](../ja/01-csi-camera-usage.md) | [한국어](../ko/01-csi-camera-usage.md) | [Português (BR)](../pt-br/01-csi-camera-usage.md) | [Português (PT)](../pt-pt/01-csi-camera-usage.md) | 简体中文 | [繁體中文](../zh-hant/01-csi-camera-usage.md)

# 01、CSI 摄像头使用

## 1、配置CSI摄像头引脚

```Plain Text
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![Screenshot from 2025\-07\-30 16\-42\-49\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

按方向键下选择**Configure Jetson 24pin CSI Connector**。然后按Enter进入下一个选项

![Screenshot from 2025\-07\-30 16\-42\-57\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

选择**Configure for compatible hardware** ，然后按Enter。

![Screenshot from 2025\-07\-30 16\-43\-09\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

按方向键下选择**Camera IMX219 Dual**，然后按Enter。

如果后面重启之后运行预览摄像头画面是报错或黑屏，这里改为Camera IMX219\-C

![Screenshot from 2025\-07\-30 16\-43\-19\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

选择**Save pin changes** ，然后按Enter。

![Screenshot from 2025\-07\-30 16\-43\-34\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

按方向键下选择**Save and reboot to reconfigure pins**，然后按Enter。

![Screenshot from 2025\-07\-30 16\-43\-53\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

出现以下界面直接按Enter键，主板会重新启动。

![Screenshot from 2025\-07\-30 16\-42\-57\.jpg](../en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

## 2、查看video设备

```Plain Text
ls /dev/video*
```

图片的结果是接了两个CSI摄像头的结果：一般一个CSI摄像头显示一个`video`设备

![Screenshot from 2025\-07\-30 16\-46\-33\.png](../en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

## 3、预览摄像头画面

终端输入下面命令，系统会自动弹出摄像头画面窗口：默认打开`/dev/video0`设备

```Plain Text
nvgstcapture-1.0
```

![Screenshot from 2025\-07\-30 16\-48\-44\.png](../en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

### 3\.1、指定摄像头

若有多个摄像头，可以指定摄像头ID：

```Plain Text
nvgstcapture-1.0 --sensor-id=1
```

![Screenshot from 2025\-07\-30 16\-55\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

### 3\.2、指定预览分辨率

若只有一个CSI摄像头，可将`--sensor-id=1`改成`--sensor-id=0`：

```Plain Text
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![Screenshot from 2025\-07\-30 16\-59\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-59-24.png)



