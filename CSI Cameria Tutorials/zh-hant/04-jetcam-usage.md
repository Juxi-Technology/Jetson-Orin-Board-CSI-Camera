[English](../en/04-jetcam-usage.md) | [Deutsch](../de/04-jetcam-usage.md) | [Español](../es/04-jetcam-usage.md) | [Français](../fr/04-jetcam-usage.md) | [Italiano](../it/04-jetcam-usage.md) | [日本語](../ja/04-jetcam-usage.md) | [한국어](../ko/04-jetcam-usage.md) | [Português (BR)](../pt-br/04-jetcam-usage.md) | [Português (PT)](../pt-pt/04-jetcam-usage.md) | [简体中文](../zh-hans/04-jetcam-usage.md) | 繁體中文

# 04、JetCam使用

JetCam使用

1、JetCam安裝

2、JetCam使用

2\.1、CSI攝像頭

主要代碼解釋

呼叫攝像頭

取得攝像頭畫面

2\.1\.1、單路攝像頭

2\.1\.2、多路攝像頭

2\.2、USB攝像頭

參考資料



JetCam 是 NVIDIA 為 Jetson 平台開發的一個易用的 Python 程式庫，用於整合和操作 USB 攝像頭或 CSI 攝像頭

## 1、JetCam安裝

```Plain Text
git clone https://github.com/NVIDIA-AI-IOT/jetcam
cd jetcam
sudo python3 setup.py install
sudo pip3 install ipywidgets
```

## 2、JetCam使用

JetCam提供典型的範例程式給使用者演示CSI和USB攝像頭的呼叫。

案例需要使用Jupyter Lab執行，使用我們出廠映像系統，可以直接透過主機板IP:8888進行存取！

### 2\.1、CSI攝像頭

Jupyter Lab網頁端進入CSI攝像頭所在資料夾並打開對應資料夾：

`/home/jetson/jetcam/notebooks/csi_camera`

**注意：對Jupyter Lab不太熟悉的，可以看Jupyter Lab使用教程了解基礎操作！**

#### 主要代碼解釋

##### 呼叫攝像頭

width：圖像輸出寬度

height：圖像輸出高度

`from jetcam.csi_camera import CSICamera`

`camera = CSICamera(width=224, height=224)`

##### 取得攝像頭畫面

`image = camera.read()`

#### 2\.1\.1、單路攝像頭

> **源碼路徑**
> 
> 

`/home/jetson/jetcam/notebooks/csi_camera/csi_camera.ipynb`

> **執行現象**
> 
> 

打開程式檔案後，單個儲存格從上往下執行：

![Screenshot from 2025\-07\-31 15\-45\-33\.png](../en/images/Screenshot%20from%202025-07-31%2015-45-33.png)

#### 2\.1\.2、多路攝像頭

> **源碼路徑**
> 
> 

`/home/jetson/jetcam/notebooks/csi_camera/multi_csi_camera.ipynb`

> **執行現象**
> 
> 

打開程式檔案後，單個儲存格從上往下執行：

![Screenshot from 2025\-07\-31 15\-53\-42\.png](../en/images/Screenshot%20from%202025-07-31%2015-53-42.png)

### 2\.2、USB攝像頭

Jupyter Lab進入USB攝像頭所在資料夾並打開檔案，出廠映像系統資料夾路徑：

`/home/jetson/jetcam/notebooks/usb_camera`

![Screenshot from 2025\-07\-31 16\-08\-19\.png](../en/images/Screenshot%20from%202025-07-31%2016-08-19.png)

## 參考資料

[https://github\.com/NVIDIA\-AI\-IOT/jetcam](https://github.com/NVIDIA-AI-IOT/jetcam)

