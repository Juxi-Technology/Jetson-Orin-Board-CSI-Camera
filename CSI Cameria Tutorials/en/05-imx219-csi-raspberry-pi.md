English | [Deutsch](../de/05-imx219-csi-raspberry-pi.md) | [Español](../es/05-imx219-csi-raspberry-pi.md) | [Français](../fr/05-imx219-csi-raspberry-pi.md) | [Italiano](../it/05-imx219-csi-raspberry-pi.md) | [日本語](../ja/05-imx219-csi-raspberry-pi.md) | [한국어](../ko/05-imx219-csi-raspberry-pi.md) | [Português (BR)](../pt-br/05-imx219-csi-raspberry-pi.md) | [Português (PT)](../pt-pt/05-imx219-csi-raspberry-pi.md) | [简体中文](../zh-hans/05-imx219-csi-raspberry-pi.md) | [繁體中文](../zh-hant/05-imx219-csi-raspberry-pi.md)

# 05. IMX219\-CSI Camera (Raspberry Pi) Tutorial

##### 1. First, use the "ls" command to check whether the vchiq device node exists: enter ls /dev

![image\.png](images/image%204.png)

If it does not exist, there may be a problem with the kernel or the device hardware; you can try reflashing the system or replacing the hardware.

##### 2. Run the "sudo raspi\-config" command to enable the Raspberry Pi CSI camera

![image\.png](images/image.png)

![image\.png](images/image%206.png)

![image\.png](images/image%205.png)

![image\.png](images/image%201.png)

Then exit and enter the command sudo reboot to restart the Raspberry Pi

##### 3. Enter "vcgencmd get\_camera" to check whether the current camera and enablement are available

![image\.png](images/image%203.png)

If detected=0, it means the camera module is not connected properly; check the hardware again. detected=1 means the CSI camera is connected normally. supported=1 means the camera has been enabled and can be used. supported=0 means the CSI camera has not been enabled and you need to enable the camera module.

## **3\. Take Photos Using the rapistill Command**

Enter **"raspistill \-o image\.jpg"** to successfully take a photo and save it; at this point the camera will light up red. For more parameters, use raspistill \-\-help

![image\.png](images/image%202.png)

Transfer the image\.jpg image to the Windows desktop and open it, and you can see the effect of the photo taken



