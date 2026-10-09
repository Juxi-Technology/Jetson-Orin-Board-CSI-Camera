[English](../en/05-imx219-csi-raspberry-pi.md) | [Deutsch](../de/05-imx219-csi-raspberry-pi.md) | [Español](../es/05-imx219-csi-raspberry-pi.md) | [Français](../fr/05-imx219-csi-raspberry-pi.md) | [Italiano](../it/05-imx219-csi-raspberry-pi.md) | [日本語](../ja/05-imx219-csi-raspberry-pi.md) | [한국어](../ko/05-imx219-csi-raspberry-pi.md) | [Português (BR)](../pt-br/05-imx219-csi-raspberry-pi.md) | [Português (PT)](../pt-pt/05-imx219-csi-raspberry-pi.md) | [简体中文](../zh-hans/05-imx219-csi-raspberry-pi.md) | 繁體中文

# 05、IMX219\-CSI攝像頭（樹莓派）教程

##### 1、首先使用"ls"指令來查看是否存在vchiq裝置節點：輸入 ls /dev

![image\.png](../en/images/image%204.png)

如果沒有，則可能是核心或者裝置硬件存在問題，可嘗試重刷系統或更換硬件。

##### 2、執行"sudo raspi\-config"命令啟用樹莓派CSI攝像頭

![image\.png](../en/images/image.png)

![image\.png](../en/images/image%206.png)

![image\.png](../en/images/image%205.png)

![image\.png](../en/images/image%201.png)

然後退出，輸入命令sudo reboot重啟下樹莓派

##### 3、輸入"vcgencmd get\_camera"查看當前攝像頭跟啟用是否可用

![image\.png](../en/images/image%203.png)

如果detected=0，說明攝像頭模組沒接好，重新排查下硬件。detected=1則說明CSI攝像頭接入正常。supported=1說明攝像頭已經啟用，攝像頭已經可以使用。supported=0則說明CSI攝像頭沒有啟用，需要啟用下攝像頭模組。

## **3\.使用rapistill命令拍照**

輸入**"raspistill \-o image\.jpg"**即可成功拍照並儲存，此時攝像頭會亮紅燈，更多參數使用raspistill \-\-help

![image\.png](../en/images/image%202.png)

將image\.jpg圖片傳輸到windows桌面打開， 即可看到拍照出來的效果



