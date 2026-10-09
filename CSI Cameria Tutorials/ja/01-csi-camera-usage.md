[English](../en/01-csi-camera-usage.md) | [Deutsch](../de/01-csi-camera-usage.md) | [Español](../es/01-csi-camera-usage.md) | [Français](../fr/01-csi-camera-usage.md) | [Italiano](../it/01-csi-camera-usage.md) | 日本語 | [한국어](../ko/01-csi-camera-usage.md) | [Português (BR)](../pt-br/01-csi-camera-usage.md) | [Português (PT)](../pt-pt/01-csi-camera-usage.md) | [简体中文](../zh-hans/01-csi-camera-usage.md) | [繁體中文](../zh-hant/01-csi-camera-usage.md)

# 01、CSIカメラの使用

## 1、CSIカメラピンの設定

```Plain Text
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![Screenshot from 2025\-07\-30 16\-42\-49\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

方向キーで下を押して**Configure Jetson 24pin CSI Connector**を選択します。その後Enterを押して次のオプションに進みます

![Screenshot from 2025\-07\-30 16\-42\-57\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

**Configure for compatible hardware** を選択し、その後Enterを押します。

![Screenshot from 2025\-07\-30 16\-43\-09\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

方向キーで下を押して**Camera IMX219 Dual**を選択し、その後Enterを押します。

後で再起動した後にカメラプレビュー画面を実行してエラーや黒画面になる場合は、ここをCamera IMX219\-Cに変更します

![Screenshot from 2025\-07\-30 16\-43\-19\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

**Save pin changes** を選択し、その後Enterを押します。

![Screenshot from 2025\-07\-30 16\-43\-34\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

方向キーで下を押して**Save and reboot to reconfigure pins**を選択し、その後Enterを押します。

![Screenshot from 2025\-07\-30 16\-43\-53\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

以下の画面が表示されたらそのままEnterキーを押すと、メインボードが再起動します。

![Screenshot from 2025\-07\-30 16\-42\-57\.jpg](../en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

## 2、videoデバイスの確認

```Plain Text
ls /dev/video*
```

図の結果はCSIカメラを2つ接続した結果です：一般的に1つのCSIカメラにつき1つの`video`デバイスが表示されます

![Screenshot from 2025\-07\-30 16\-46\-33\.png](../en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

## 3、カメラ映像のプレビュー

ターミナルで以下のコマンドを入力すると、システムが自動的にカメラ画面のウィンドウをポップアップ表示します：デフォルトでは`/dev/video0`デバイスを開きます

```Plain Text
nvgstcapture-1.0
```

![Screenshot from 2025\-07\-30 16\-48\-44\.png](../en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

### 3\.1、カメラの指定

カメラが複数ある場合は、カメラIDを指定できます：

```Plain Text
nvgstcapture-1.0 --sensor-id=1
```

![Screenshot from 2025\-07\-30 16\-55\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

### 3\.2、プレビュー解像度の指定

CSIカメラが1つだけの場合、`--sensor-id=1`を`--sensor-id=0`に変更できます：

```Plain Text
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![Screenshot from 2025\-07\-30 16\-59\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-59-24.png)



