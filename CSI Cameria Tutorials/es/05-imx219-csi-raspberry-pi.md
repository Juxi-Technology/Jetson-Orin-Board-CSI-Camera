[English](../en/05-imx219-csi-raspberry-pi.md) | [Deutsch](../de/05-imx219-csi-raspberry-pi.md) | Español | [Français](../fr/05-imx219-csi-raspberry-pi.md) | [Italiano](../it/05-imx219-csi-raspberry-pi.md) | [日本語](../ja/05-imx219-csi-raspberry-pi.md) | [한국어](../ko/05-imx219-csi-raspberry-pi.md) | [Português (BR)](../pt-br/05-imx219-csi-raspberry-pi.md) | [Português (PT)](../pt-pt/05-imx219-csi-raspberry-pi.md) | [简体中文](../zh-hans/05-imx219-csi-raspberry-pi.md) | [繁體中文](../zh-hant/05-imx219-csi-raspberry-pi.md)

# 05. Tutorial de la cámara IMX219\-CSI (Raspberry Pi)

##### 1. En primer lugar, utilice el comando "ls" para comprobar si existe el nodo de dispositivo vchiq: introduzca ls /dev

![image\.png](../en/images/image%204.png)

Si no existe, puede deberse a un problema del kernel o del hardware del dispositivo; puede intentar volver a grabar el sistema o cambiar el hardware.

##### 2. Ejecute el comando "sudo raspi\-config" para habilitar la cámara CSI de Raspberry Pi

![image\.png](../en/images/image.png)

![image\.png](../en/images/image%206.png)

![image\.png](../en/images/image%205.png)

![image\.png](../en/images/image%201.png)

A continuación, salga y ejecute el comando sudo reboot para reiniciar la Raspberry Pi

##### 3. Introduzca "vcgencmd get\_camera" para comprobar si la cámara actual y su habilitación están disponibles

![image\.png](../en/images/image%203.png)

Si detected=0, significa que el módulo de cámara no está bien conectado; revise de nuevo el hardware. detected=1 indica que la cámara CSI está conectada correctamente. supported=1 indica que la cámara ya está habilitada y puede utilizarse. supported=0 indica que la cámara CSI no está habilitada y es necesario habilitar el módulo de cámara.

## **3\. Tomar fotografías con el comando rapistill**

Introduzca **"raspistill \-o image\.jpg"** para tomar y guardar la fotografía correctamente; en ese momento la cámara encenderá una luz roja. Para más parámetros, utilice raspistill \-\-help

![image\.png](../en/images/image%202.png)

Transfiera la imagen image\.jpg al escritorio de Windows y ábrala para ver el resultado de la fotografía



