[English](../en/05-imx219-csi-raspberry-pi.md) | [Deutsch](../de/05-imx219-csi-raspberry-pi.md) | [Español](../es/05-imx219-csi-raspberry-pi.md) | [Français](../fr/05-imx219-csi-raspberry-pi.md) | [Italiano](../it/05-imx219-csi-raspberry-pi.md) | [日本語](../ja/05-imx219-csi-raspberry-pi.md) | [한국어](../ko/05-imx219-csi-raspberry-pi.md) | [Português (BR)](../pt-br/05-imx219-csi-raspberry-pi.md) | [Português (PT)](../pt-pt/05-imx219-csi-raspberry-pi.md) | 简体中文 | [繁體中文](../zh-hant/05-imx219-csi-raspberry-pi.md)

# 05、IMX219\-CSI摄像头（树莓派）教程

##### 1、首先使用"ls"指令来查看是否存在vchiq设备节点：输入 ls /dev

![image\.png](../en/images/image%204.png)

如果没有，则可能是内核或者设备硬件存在问题，可尝试重刷系统或更换硬件。

##### 2、运行"sudo raspi\-config"命令使能树莓派CSI摄像头

![image\.png](../en/images/image.png)

![image\.png](../en/images/image%206.png)

![image\.png](../en/images/image%205.png)

![image\.png](../en/images/image%201.png)

然后退出，输入命令sudo reboot重启下树莓派

##### 3、输入"vcgencmd get\_camera"查看当前摄像头跟使能是否可用

![image\.png](../en/images/image%203.png)

如果detected=0，说明摄像头模块没接好，重新排查下硬件。detected=1则说明CSI摄像头接入正常。supported=1说明摄像头已经使能，摄像头已经可以使用。supported=0则说明CSI摄像头没有使能，需要使能下摄像头模块。

## **3\.使用rapistill命令拍照**

输入**"raspistill \-o image\.jpg"**即可成功拍照并保存，此时摄像头会亮红灯，更多参数使用raspistill \-\-help

![image\.png](../en/images/image%202.png)

将image\.jpg图片传输到windows桌面打开， 即可看到拍照出来的效果



