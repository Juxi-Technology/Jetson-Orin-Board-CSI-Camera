[English](../en/01-csi-camera-usage.md) | [Deutsch](../de/01-csi-camera-usage.md) | [Español](../es/01-csi-camera-usage.md) | [Français](../fr/01-csi-camera-usage.md) | [Italiano](../it/01-csi-camera-usage.md) | [日本語](../ja/01-csi-camera-usage.md) | [한국어](../ko/01-csi-camera-usage.md) | [Português (BR)](../pt-br/01-csi-camera-usage.md) | [Português (PT)](../pt-pt/01-csi-camera-usage.md) | [简体中文](../zh-hans/01-csi-camera-usage.md) | 繁體中文

# 01、CSI 攝像頭使用

## 1、配置CSI攝像頭引腳

```Plain Text
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![Screenshot from 2025\-07\-30 16\-42\-49\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

按方向鍵下選擇**Configure Jetson 24pin CSI Connector**。然後按Enter進入下一個選項

![Screenshot from 2025\-07\-30 16\-42\-57\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

選擇**Configure for compatible hardware** ，然後按Enter。

![Screenshot from 2025\-07\-30 16\-43\-09\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

按方向鍵下選擇**Camera IMX219 Dual**，然後按Enter。

如果後面重啟之後執行預覽攝像頭畫面是報錯或黑屏，這裡改為Camera IMX219\-C

![Screenshot from 2025\-07\-30 16\-43\-19\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

選擇**Save pin changes** ，然後按Enter。

![Screenshot from 2025\-07\-30 16\-43\-34\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

按方向鍵下選擇**Save and reboot to reconfigure pins**，然後按Enter。

![Screenshot from 2025\-07\-30 16\-43\-53\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

出現以下介面直接按Enter鍵，主機板會重新啟動。

![Screenshot from 2025\-07\-30 16\-42\-57\.jpg](../en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

## 2、查看video裝置

```Plain Text
ls /dev/video*
```

圖片的結果是接了兩個CSI攝像頭的結果：一般一個CSI攝像頭顯示一個`video`裝置

![Screenshot from 2025\-07\-30 16\-46\-33\.png](../en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

## 3、預覽攝像頭畫面

終端輸入下面命令，系統會自動彈出攝像頭畫面視窗：預設打開`/dev/video0`裝置

```Plain Text
nvgstcapture-1.0
```

![Screenshot from 2025\-07\-30 16\-48\-44\.png](../en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

### 3\.1、指定攝像頭

若有多個攝像頭，可以指定攝像頭ID：

```Plain Text
nvgstcapture-1.0 --sensor-id=1
```

![Screenshot from 2025\-07\-30 16\-55\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

### 3\.2、指定預覽解像度

若只有一個CSI攝像頭，可將`--sensor-id=1`改成`--sensor-id=0`：

```Plain Text
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![Screenshot from 2025\-07\-30 16\-59\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-59-24.png)



