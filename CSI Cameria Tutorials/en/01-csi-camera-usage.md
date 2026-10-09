English | [Deutsch](../de/01-csi-camera-usage.md) | [Español](../es/01-csi-camera-usage.md) | [Français](../fr/01-csi-camera-usage.md) | [Italiano](../it/01-csi-camera-usage.md) | [日本語](../ja/01-csi-camera-usage.md) | [한국어](../ko/01-csi-camera-usage.md) | [Português (BR)](../pt-br/01-csi-camera-usage.md) | [Português (PT)](../pt-pt/01-csi-camera-usage.md) | [简体中文](../zh-hans/01-csi-camera-usage.md) | [繁體中文](../zh-hant/01-csi-camera-usage.md)

# 01. CSI Camera Usage

## 1. Configure CSI Camera Pins

```Plain Text
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![Screenshot from 2025\-07\-30 16\-42\-49\.png](images/Screenshot%20from%202025-07-30%2016-42-49.png)

Press the Down arrow key to select **Configure Jetson 24pin CSI Connector**. Then press Enter to proceed to the next option

![Screenshot from 2025\-07\-30 16\-42\-57\.png](images/Screenshot%20from%202025-07-30%2016-42-57.png)

Select **Configure for compatible hardware** , then press Enter.

![Screenshot from 2025\-07\-30 16\-43\-09\.png](images/Screenshot%20from%202025-07-30%2016-43-09.png)

Press the Down arrow key to select **Camera IMX219 Dual**, then press Enter.

If running the camera preview after the subsequent restart reports an error or shows a black screen, change this to Camera IMX219\-C

![Screenshot from 2025\-07\-30 16\-43\-19\.png](images/Screenshot%20from%202025-07-30%2016-43-19.png)

Select **Save pin changes** , then press Enter.

![Screenshot from 2025\-07\-30 16\-43\-34\.png](images/Screenshot%20from%202025-07-30%2016-43-34.png)

Press the Down arrow key to select **Save and reboot to reconfigure pins**, then press Enter.

![Screenshot from 2025\-07\-30 16\-43\-53\.png](images/Screenshot%20from%202025-07-30%2016-43-53.png)

When the following screen appears, press Enter directly, and the board will restart.

![Screenshot from 2025\-07\-30 16\-42\-57\.jpg](images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

## 2. View Video Devices

```Plain Text
ls /dev/video*
```

The result in the image is the result of connecting two CSI cameras: generally, one CSI camera shows one `video` device

![Screenshot from 2025\-07\-30 16\-46\-33\.png](images/Screenshot%20from%202025-07-30%2016-46-33.png)

## 3. Preview the Camera Image

Enter the following command in the terminal, and the system will automatically pop up a camera image window: it opens the `/dev/video0` device by default

```Plain Text
nvgstcapture-1.0
```

![Screenshot from 2025\-07\-30 16\-48\-44\.png](images/Screenshot%20from%202025-07-30%2016-48-44.png)

### 3\.1. Specify the Camera

If there are multiple cameras, you can specify the camera ID:

```Plain Text
nvgstcapture-1.0 --sensor-id=1
```

![Screenshot from 2025\-07\-30 16\-55\-24\.png](images/Screenshot%20from%202025-07-30%2016-55-24.png)

### 3\.2. Specify the Preview Resolution

If there is only one CSI camera, you can change `--sensor-id=1` to `--sensor-id=0`:

```Plain Text
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![Screenshot from 2025\-07\-30 16\-59\-24\.png](images/Screenshot%20from%202025-07-30%2016-59-24.png)



