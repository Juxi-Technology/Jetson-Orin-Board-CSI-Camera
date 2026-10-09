[English](README.md) | 简体中文

# Jetson Orin 开发板 CSI 摄像头配置教程

NVIDIA Jetson Orin 开发板的 CSI 摄像头配置与使用指南 —— 接口引脚复用、设备检查、实时预览、自动对焦摄像头、JupyterLab、JetCam，以及树莓派上的 IMX219 摄像头。

每篇教程都提供 11 种语言版本。图片**只存放在 `CSI Cameria Tutorials/en/images/` 一份**，其他语言的教程统一引用这一份。

## 语言

| 语言 | 目录 |
|------|------|
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

## 教程列表

| 序号 | 中文 | English |
|------|------|---------|
| 01 | [CSI 摄像头使用](CSI%20Cameria%20Tutorials/zh-hans/01-csi-camera-usage.md) | [CSI Camera Usage](CSI%20Cameria%20Tutorials/en/01-csi-camera-usage.md) |
| 02 | [自动对焦摄像头使用](CSI%20Cameria%20Tutorials/zh-hans/02-autofocus-camera-usage.md) | [Auto-Focus Camera Usage](CSI%20Cameria%20Tutorials/en/02-autofocus-camera-usage.md) |
| 03 | [Jupyter Lab 使用](CSI%20Cameria%20Tutorials/zh-hans/03-jupyterlab-usage.md) | [JupyterLab Usage](CSI%20Cameria%20Tutorials/en/03-jupyterlab-usage.md) |
| 04 | [JetCam 使用](CSI%20Cameria%20Tutorials/zh-hans/04-jetcam-usage.md) | [JetCam Usage](CSI%20Cameria%20Tutorials/en/04-jetcam-usage.md) |
| 05 | [IMX219-CSI 摄像头（树莓派）教程](CSI%20Cameria%20Tutorials/zh-hans/05-imx219-csi-raspberry-pi.md) | [IMX219 CSI Camera (Raspberry Pi)](CSI%20Cameria%20Tutorials/en/05-imx219-csi-raspberry-pi.md) |

每篇教程首行都有语言切换条，可在同一教程的不同语言版本间跳转。另外 9 种语言见 [`index.md`](CSI%20Cameria%20Tutorials/zh-hans/index.md)。

## 快速开始

### 1. 配置 CSI 摄像头引脚

```
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![jetson-io 主菜单](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

按方向键 ↓ 选中 `Configure Jetson 24pin CSI Connector`，按 `Enter` 进入下一项。

![Configure Jetson 24pin CSI Connector](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

选择 `Configure for compatible hardware`，按 `Enter`。

![Configure for compatible hardware](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

按方向键 ↓ 选中 `Camera IMX219 Dual`，按 `Enter`。

![Camera IMX219 Dual](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

选择 `Save pin changes`，按 `Enter`。

![Save pin changes](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

按方向键 ↓ 选中 `Save and reboot to reconfigure pins`，按 `Enter`。

![Save and reboot to reconfigure pins](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

出现下面的界面时直接按 `Enter`，开发板会重启。

![重启确认](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

> 重启后如果摄像头预览报错或黑屏，重新运行 `jetson-io.py`，改选 `Camera IMX219-C`。

### 2. 检查视频设备

```
ls /dev/video*
```

一般一个 CSI 摄像头对应一个 `video` 设备。下图是接了**两个** CSI 摄像头的结果。

![视频设备](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

### 3. 预览摄像头画面

```
nvgstcapture-1.0
```

系统会自动弹出预览窗口，默认打开 `/dev/video0`。

![nvgstcapture 预览](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

有多个摄像头时，可以指定摄像头编号：

```
nvgstcapture-1.0 --sensor-id=1
```

![指定摄像头](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

也可以同时指定预览分辨率 —— 如果只有一个 CSI 摄像头，把 `--sensor-id=1` 改成 `--sensor-id=0`：

```
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![指定预览分辨率](CSI%20Cameria%20Tutorials/en/images/Screenshot%20from%202025-07-30%2016-59-24.png)

## 说明

- 一个 CSI 摄像头显示一个 `/dev/video*` 设备，一个 USB 摄像头会显示**两个**。若 USB 摄像头新增了 `/dev/video2` 和 `/dev/video3`，使用编号较小的 `/dev/video2`。
- `nvgstcapture-1.0` 只能打开 CSI 摄像头。USB 摄像头和自动对焦摄像头请用 [GUVCView 或 VLC](CSI%20Cameria%20Tutorials/zh-hans/02-autofocus-camera-usage.md) —— 这两者都看不到 CSI 摄像头的画面。
