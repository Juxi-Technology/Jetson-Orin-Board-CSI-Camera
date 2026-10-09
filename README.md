English | [简体中文](README_CN.md)

# Jetson Orin Board CSI Camera Setup Guide

Configuration and usage guide for CSI cameras on NVIDIA Jetson Orin boards — connector pin muxing, device verification, live preview, auto-focus cameras, JupyterLab, JetCam, and the IMX219 camera on Raspberry Pi.

Every tutorial is available in 11 languages. Images are stored **only** under `CSI Cameria Tutorials/en/images/`; all other language trees link to that one copy.

## Language

| Language | Folder |
|----------|--------|
| English | [`en/`](CSI%20Cameria%20Tutorials/en/) |
| Deutsch | [`de/`](CSI%20Cameria%20Tutorials/de/) |
| Español | [`es/`](CSI%20Cameria%20Tutorials/es/) |
| Français | [`fr/`](CSI%20Cameria%20Tutorials/fr/) |
| Italiano | [`it/`](CSI%20Cameria%20Tutorials/it/) |
| 日本語 | [`ja/`](CSI%20Cameria%20Tutorials/ja/) |
| 한국어 | [`ko/`](CSI%20Cameria%20Tutorials/ko/) |
| Português (BR) | [`pt-br/`](CSI%20Cameria%20Tutorials/pt-br/) |
| Português (PT) | [`pt-pt/`](CSI%20Cameria%20Tutorials/pt-pt/) |
| 简体中文 | [`zh-hans/`](CSI%20Cameria%20Tutorials/zh-hans/) |
| 繁體中文 | [`zh-hant/`](CSI%20Cameria%20Tutorials/zh-hant/) |

## Tutorials

| # | English | 中文 |
|---|---------|------|
| 01 | [CSI Camera Usage](CSI%20Cameria%20Tutorials/en/01-csi-camera-usage.md) | [CSI 摄像头使用](CSI%20Cameria%20Tutorials/zh-hans/01-csi-camera-usage.md) |
| 02 | [Auto-Focus Camera Usage](CSI%20Cameria%20Tutorials/en/02-autofocus-camera-usage.md) | [自动对焦摄像头使用](CSI%20Cameria%20Tutorials/zh-hans/02-autofocus-camera-usage.md) |
| 03 | [JupyterLab Usage](CSI%20Cameria%20Tutorials/en/03-jupyterlab-usage.md) | [Jupyter Lab 使用](CSI%20Cameria%20Tutorials/zh-hans/03-jupyterlab-usage.md) |
| 04 | [JetCam Usage](CSI%20Cameria%20Tutorials/en/04-jetcam-usage.md) | [JetCam 使用](CSI%20Cameria%20Tutorials/zh-hans/04-jetcam-usage.md) |
| 05 | [IMX219 CSI Camera (Raspberry Pi)](CSI%20Cameria%20Tutorials/en/05-imx219-csi-raspberry-pi.md) | [IMX219-CSI 摄像头（树莓派）教程](CSI%20Cameria%20Tutorials/zh-hans/05-imx219-csi-raspberry-pi.md) |

Each tutorial page carries a language switcher on its first line, so you can jump between languages at the same stage. The other nine languages are indexed in [`index.md`](CSI%20Cameria%20Tutorials/en/index.md).

## Quick Start

### 1. Configure the CSI Camera Pins

```
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![jetson-io main menu](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

Press the Down arrow key to select `Configure Jetson 24pin CSI Connector`, then press `Enter`.

![Configure Jetson 24pin CSI Connector](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

Select `Configure for compatible hardware`, then press `Enter`.

![Configure for compatible hardware](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

Press the Down arrow key to select `Camera IMX219 Dual`, then press `Enter`.

![Camera IMX219 Dual](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

Select `Save pin changes`, then press `Enter`.

![Save pin changes](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

Press the Down arrow key to select `Save and reboot to reconfigure pins`, then press `Enter`.

![Save and reboot to reconfigure pins](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

When the following screen appears, press `Enter` and the board will reboot.

![Reboot confirmation](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

> If the camera preview reports an error or shows a black screen after the reboot, re-run `jetson-io.py` and pick `Camera IMX219-C` instead.

### 2. Check the Video Devices

```
ls /dev/video*
```

Generally one CSI camera shows one `video` device. The image below is the result with two CSI cameras connected.

![video devices](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

### 3. Preview the Camera Feed

```
nvgstcapture-1.0
```

This opens a preview window on `/dev/video0` by default.

![nvgstcapture preview](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

Pick a specific camera by sensor ID:

```
nvgstcapture-1.0 --sensor-id=1
```

![specify sensor id](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

Set the preview resolution as well — with a single CSI camera, change `--sensor-id=1` to `--sensor-id=0`:

```
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![specify preview resolution](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-59-24.png)

## Notes

- One CSI camera shows one `/dev/video*` device; a USB camera shows **two**. For a USB camera that adds `/dev/video2` and `/dev/video3`, use the lower-numbered `/dev/video2`.
- `nvgstcapture-1.0` opens CSI cameras only. For USB and auto-focus cameras use [GUVCView or VLC](CSI%20Cameria%20Tutorials/en/02-autofocus-camera-usage.md) — in both, the CSI camera has no preview image.
