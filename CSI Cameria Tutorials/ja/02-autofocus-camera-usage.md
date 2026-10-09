[English](../en/02-autofocus-camera-usage.md) | [Deutsch](../de/02-autofocus-camera-usage.md) | [Español](../es/02-autofocus-camera-usage.md) | [Français](../fr/02-autofocus-camera-usage.md) | [Italiano](../it/02-autofocus-camera-usage.md) | 日本語 | [한국어](../ko/02-autofocus-camera-usage.md) | [Português (BR)](../pt-br/02-autofocus-camera-usage.md) | [Português (PT)](../pt-pt/02-autofocus-camera-usage.md) | [简体中文](../zh-hans/02-autofocus-camera-usage.md) | [繁體中文](../zh-hant/02-autofocus-camera-usage.md)

# 02、オートフォーカスカメラの使用

## 1、videoデバイスの確認

```Plain Text
ls /dev/video*
```

図の結果はCSIカメラ2つ、USBカメラ1つを接続した結果です：一般的に1つのCSIカメラにつき1つの`video`デバイスが表示され、1つのUSBカメラにつき2つの`video`デバイスが表示されます。USBカメラは新しく追加された、番号が小さい`/dev/video2`を選択して呼び出します（USBカメラを接続するとシステムに`/dev/video2`、`/dev/video3`のデバイス番号が新規追加されます）

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

## 2、GUVCView

GUVCViewはLinuxシステム用のオープンソースソフトウェアで、ビデオや画像のキャプチャと録画に使用され、主にWebcamカメラに用いられます。

### 2\.1、GUVCViewのインストール

```Plain Text
sudo apt update
sudo apt install guvcview -y
```

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

### 2\.2、GUVCViewの使用

アプリケーションメニューバーで`guvcview`アイコンをクリックするか、ターミナルで起動コマンドを入力します：USBカメラを選択してください。CSIカメラはプレビュー画面がありません

```Plain Text
guvcview
```

![截图\_20250925170724\.png](../en/images/截图_20250925170724.png)

![Screenshot from 2025\-07\-30 17\-04\-00\.png](../en/images/Screenshot%20from%202025-07-30%2017-04-00.png)

## 3、VLC

VLC media playerは自由かつオープンソースのマルチメディアプレーヤーで、さまざまな音声・動画フォーマット、およびDVD、オーディオCD、VCDと各種ストリーミングプロトコルをサポートします。

### 3\.1、VLCのインストール

```Plain Text
sudo apt update
sudo apt install vlc -y
```

![Screenshot from 2025\-07\-30 17\-05\-31\.png](../en/images/Screenshot%20from%202025-07-30%2017-05-31.png)

### 3\.2、VLCの使用

アプリケーションメニューバーで`VLC media player`アイコンをクリックするか、ターミナルで起動コマンドを入力します：USBカメラを選択してください。CSIカメラはプレビュー画面がありません

```Plain Text
vlc
```

![Screenshot from 2025\-07\-30 17\-06\-32\.png](../en/images/Screenshot%20from%202025-07-30%2017-06-32.png)

![Screenshot from 2025\-07\-30 17\-07\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-07-09.png)

USBカメラに対応するデバイス番号を選択します：

![截图\_20250925170820\.png](../en/images/截图_20250925170820.png)

![Screenshot from 2025\-07\-30 17\-08\-35\.png](../en/images/Screenshot%20from%202025-07-30%2017-08-35.png)



