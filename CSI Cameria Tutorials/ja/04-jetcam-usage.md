[English](../en/04-jetcam-usage.md) | [Deutsch](../de/04-jetcam-usage.md) | [Español](../es/04-jetcam-usage.md) | [Français](../fr/04-jetcam-usage.md) | [Italiano](../it/04-jetcam-usage.md) | 日本語 | [한국어](../ko/04-jetcam-usage.md) | [Português (BR)](../pt-br/04-jetcam-usage.md) | [Português (PT)](../pt-pt/04-jetcam-usage.md) | [简体中文](../zh-hans/04-jetcam-usage.md) | [繁體中文](../zh-hant/04-jetcam-usage.md)

# 04、JetCamの使用

JetCamの使用

1、JetCamのインストール

2、JetCamの使用

2\.1、CSIカメラ

主要コードの解説

カメラの呼び出し

カメラ映像の取得

2\.1\.1、単一カメラ

2\.1\.2、複数カメラ

2\.2、USBカメラ

参考資料



JetCam は NVIDIA が Jetson プラットフォーム向けに開発した使いやすい Python ライブラリで、USB カメラや CSI カメラの統合と操作に使用されます

## 1、JetCamのインストール

```Plain Text
git clone https://github.com/NVIDIA-AI-IOT/jetcam
cd jetcam
sudo python3 setup.py install
sudo pip3 install ipywidgets
```

## 2、JetCamの使用

JetCamは典型的なサンプルプログラムを提供し、ユーザーにCSIカメラとUSBカメラの呼び出しをデモンストレーションします。

サンプルはJupyter Labで実行する必要があります。当社の出荷イメージシステムを使用している場合、メインボードIP:8888から直接アクセスできます！

### 2\.1、CSIカメラ

Jupyter LabのWeb画面でCSIカメラが格納されているフォルダに移動し、対応するフォルダを開きます：

`/home/jetson/jetcam/notebooks/csi_camera`

**注意：Jupyter Labにあまり慣れていない方は、Jupyter Lab使用チュートリアルを見て基本操作を確認できます！**

#### 主要コードの解説

##### カメラの呼び出し

width：画像出力の幅

height：画像出力の高さ

`from jetcam.csi_camera import CSICamera`

`camera = CSICamera(width=224, height=224)`

##### カメラ映像の取得

`image = camera.read()`

#### 2\.1\.1、単一カメラ

> **ソースコードのパス**
> 
> 

`/home/jetson/jetcam/notebooks/csi_camera/csi_camera.ipynb`

> **実行結果**
> 
> 

プログラムファイルを開いた後、個々のセルを上から下へ順に実行します：

![Screenshot from 2025\-07\-31 15\-45\-33\.png](../en/images/Screenshot%20from%202025-07-31%2015-45-33.png)

#### 2\.1\.2、複数カメラ

> **ソースコードのパス**
> 
> 

`/home/jetson/jetcam/notebooks/csi_camera/multi_csi_camera.ipynb`

> **実行結果**
> 
> 

プログラムファイルを開いた後、個々のセルを上から下へ順に実行します：

![Screenshot from 2025\-07\-31 15\-53\-42\.png](../en/images/Screenshot%20from%202025-07-31%2015-53-42.png)

### 2\.2、USBカメラ

Jupyter LabでUSBカメラが格納されているフォルダに移動し、ファイルを開きます。出荷イメージシステムのフォルダパス：

`/home/jetson/jetcam/notebooks/usb_camera`

![Screenshot from 2025\-07\-31 16\-08\-19\.png](../en/images/Screenshot%20from%202025-07-31%2016-08-19.png)

## 参考資料

[https://github\.com/NVIDIA\-AI\-IOT/jetcam](https://github.com/NVIDIA-AI-IOT/jetcam)

