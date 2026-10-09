[English](../en/05-imx219-csi-raspberry-pi.md) | [Deutsch](../de/05-imx219-csi-raspberry-pi.md) | [Español](../es/05-imx219-csi-raspberry-pi.md) | [Français](../fr/05-imx219-csi-raspberry-pi.md) | [Italiano](../it/05-imx219-csi-raspberry-pi.md) | 日本語 | [한국어](../ko/05-imx219-csi-raspberry-pi.md) | [Português (BR)](../pt-br/05-imx219-csi-raspberry-pi.md) | [Português (PT)](../pt-pt/05-imx219-csi-raspberry-pi.md) | [简体中文](../zh-hans/05-imx219-csi-raspberry-pi.md) | [繁體中文](../zh-hant/05-imx219-csi-raspberry-pi.md)

# 05、IMX219\-CSIカメラ（Raspberry Pi）チュートリアル

##### 1、まず"ls"コマンドを使用してvchiqデバイスノードが存在するか確認します：ls /dev を入力

![image\.png](../en/images/image%204.png)

存在しない場合、カーネルまたはデバイスハードウェアに問題がある可能性があります。システムを再インストールするか、ハードウェアを交換してみてください。

##### 2、"sudo raspi\-config"コマンドを実行してRaspberry PiのCSIカメラを有効にします

![image\.png](../en/images/image.png)

![image\.png](../en/images/image%206.png)

![image\.png](../en/images/image%205.png)

![image\.png](../en/images/image%201.png)

その後終了し、コマンドsudo rebootを入力してRaspberry Piを再起動します

##### 3、"vcgencmd get\_camera"を入力して現在のカメラと有効化が使用可能か確認します

![image\.png](../en/images/image%203.png)

detected=0の場合、カメラモジュールが正しく接続されていないことを示すため、ハードウェアを再確認してください。detected=1の場合はCSIカメラの接続が正常であることを示します。supported=1はカメラが有効化されており、カメラが使用可能であることを示します。supported=0の場合はCSIカメラが有効化されていないことを示すため、カメラモジュールを有効化する必要があります。

## **3\.rapistillコマンドを使用して撮影**

**"raspistill \-o image\.jpg"**を入力すると撮影と保存に成功します。このときカメラの赤色ランプが点灯します。その他のパラメータはraspistill \-\-helpを使用してください

![image\.png](../en/images/image%202.png)

image\.jpg画像をWindowsデスクトップに転送して開くと、撮影された結果を確認できます



