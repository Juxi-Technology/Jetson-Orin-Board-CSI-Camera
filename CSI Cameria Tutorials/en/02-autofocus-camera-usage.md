English | [Deutsch](../de/02-autofocus-camera-usage.md) | [Español](../es/02-autofocus-camera-usage.md) | [Français](../fr/02-autofocus-camera-usage.md) | [Italiano](../it/02-autofocus-camera-usage.md) | [日本語](../ja/02-autofocus-camera-usage.md) | [한국어](../ko/02-autofocus-camera-usage.md) | [Português (BR)](../pt-br/02-autofocus-camera-usage.md) | [Português (PT)](../pt-pt/02-autofocus-camera-usage.md) | [简体中文](../zh-hans/02-autofocus-camera-usage.md) | [繁體中文](../zh-hant/02-autofocus-camera-usage.md)

# 02. Auto-Focus Camera Usage

## 1. View Video Devices

```Plain Text
ls /dev/video*
```

The result in the image is the result of connecting two CSI cameras and one USB camera: generally, one CSI camera shows one `video` device, and one USB camera shows two `video` devices. For the USB camera, choose the newly added `/dev/video2` with the smaller number to use it (connecting the USB camera adds the `/dev/video2` and `/dev/video3` device numbers to the system)

![Screenshot from 2025\-07\-30 17\-01\-09\.png](images/Screenshot%20from%202025-07-30%2017-01-09.png)

## 2. GUVCView

GUVCView is open-source software for Linux systems, used to capture and record video and images, mainly for webcam cameras.

### 2\.1. GUVCView Installation

```Plain Text
sudo apt update
sudo apt install guvcview -y
```

![Screenshot from 2025\-07\-30 17\-01\-09\.png](images/Screenshot%20from%202025-07-30%2017-01-09.png)

### 2\.2. GUVCView Usage

Go to the application menu bar and click the `guvcview` icon, or enter the launch command in the terminal: select the USB camera; the CSI camera has no preview image

```Plain Text
guvcview
```

![截图\_20250925170724\.png](images/截图_20250925170724.png)

![Screenshot from 2025\-07\-30 17\-04\-00\.png](images/Screenshot%20from%202025-07-30%2017-04-00.png)

## 3. VLC

VLC media player is a free and open-source multimedia player that supports multiple audio and video formats as well as DVD, audio CD, VCD, and various streaming protocols.

### 3\.1. VLC Installation

```Plain Text
sudo apt update
sudo apt install vlc -y
```

![Screenshot from 2025\-07\-30 17\-05\-31\.png](images/Screenshot%20from%202025-07-30%2017-05-31.png)

### 3\.2. VLC Usage

Go to the application menu bar and click the `VLC media player` icon, or enter the launch command in the terminal: select the USB camera; the CSI camera has no preview image

```Plain Text
vlc
```

![Screenshot from 2025\-07\-30 17\-06\-32\.png](images/Screenshot%20from%202025-07-30%2017-06-32.png)

![Screenshot from 2025\-07\-30 17\-07\-09\.png](images/Screenshot%20from%202025-07-30%2017-07-09.png)

Select the device number corresponding to the USB camera:

![截图\_20250925170820\.png](images/截图_20250925170820.png)

![Screenshot from 2025\-07\-30 17\-08\-35\.png](images/Screenshot%20from%202025-07-30%2017-08-35.png)



