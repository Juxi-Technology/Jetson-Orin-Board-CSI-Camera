[English](../en/02-autofocus-camera-usage.md) | [Deutsch](../de/02-autofocus-camera-usage.md) | [Español](../es/02-autofocus-camera-usage.md) | [Français](../fr/02-autofocus-camera-usage.md) | [Italiano](../it/02-autofocus-camera-usage.md) | [日本語](../ja/02-autofocus-camera-usage.md) | [한국어](../ko/02-autofocus-camera-usage.md) | [Português (BR)](../pt-br/02-autofocus-camera-usage.md) | [Português (PT)](../pt-pt/02-autofocus-camera-usage.md) | [简体中文](../zh-hans/02-autofocus-camera-usage.md) | 繁體中文

# 02、自動對焦攝像頭使用

## 1、查看video裝置

```Plain Text
ls /dev/video*
```

圖片的結果是接了兩個CSI攝像頭、一個USB攝像頭的結果：一般一個CSI攝像頭顯示一個`video`裝置，一個USB攝像頭顯示兩個`video`裝置，USB攝像頭選擇新增加且數字較小的`/dev/video2`呼叫（接上USB攝像頭系統新增`/dev/video2`、`/dev/video3`裝置號）

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

## 2、GUVCView

GUVCView是一個用於Linux系統的開源軟件，用於捕捉和錄製影片和圖像，主要用於Webcam攝像頭。

### 2\.1、GUVCView安裝

```Plain Text
sudo apt update
sudo apt install guvcview -y
```

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

### 2\.2、GUVCView使用

進入應用選單欄點擊`guvcview`圖示或者終端輸入啟動命令：選擇USB攝像頭，CSI攝像頭無預覽畫面

```Plain Text
guvcview
```

![截图\_20250925170724\.png](../en/images/截图_20250925170724.png)

![Screenshot from 2025\-07\-30 17\-04\-00\.png](../en/images/Screenshot%20from%202025-07-30%2017-04-00.png)

## 3、VLC

VLC media player是一個自由且開源的多媒體播放器，支援多種音訊和影片格式以及DVD、音訊CD、VCD和各種串流媒體協定。

### 3\.1、VLC安裝

```Plain Text
sudo apt update
sudo apt install vlc -y
```

![Screenshot from 2025\-07\-30 17\-05\-31\.png](../en/images/Screenshot%20from%202025-07-30%2017-05-31.png)

### 3\.2、VLC使用

進入應用選單欄點擊`VLC media player`圖示或者終端輸入啟動命令：選擇USB攝像頭，CSI攝像頭無預覽畫面

```Plain Text
vlc
```

![Screenshot from 2025\-07\-30 17\-06\-32\.png](../en/images/Screenshot%20from%202025-07-30%2017-06-32.png)

![Screenshot from 2025\-07\-30 17\-07\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-07-09.png)

選擇USB攝像頭對應的裝置號：

![截图\_20250925170820\.png](../en/images/截图_20250925170820.png)

![Screenshot from 2025\-07\-30 17\-08\-35\.png](../en/images/Screenshot%20from%202025-07-30%2017-08-35.png)



