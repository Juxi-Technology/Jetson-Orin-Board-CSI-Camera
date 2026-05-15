# Jetson-Orin-Board-CSI-Camera-Setup-Guide

## 1. Configure CSI Camera Pins
```
sudo /opt/nvidia/jetson-io/jetson-io.py
```
![Insert image description here](https://i-blog.csdnimg.cn/direct/ecc10d3cb6c5478f90c040f371796a0e.png)
Press the down arrow key to select `Configure Jetson 24pin CSI Connector`. Then press `Enter` to proceed to the next option.
![Insert image description here](https://i-blog.csdnimg.cn/direct/9003459212d442029a30b673c448ef28.png)
Select `Configure for compatible hardware`, then press `Enter`.
![Insert image description here](https://i-blog.csdnimg.cn/direct/3672c85eb2da4e899fd1dd342e5a23dc.png)
Press the down arrow key to select `Camera IMX219 Dual`, then press `Enter`.
![Insert image description here](https://i-blog.csdnimg.cn/direct/e57720d35b3a443598c486d6c95d9cca.png)
Select `Save pin changes`, then press `Enter`.
![Insert image description here](https://i-blog.csdnimg.cn/direct/91a24524dfb94e29bde6057b9a2db919.png)
Press the down arrow key to select `Save and reboot to reconfigure pins`, then press `Enter`.
![Insert image description here](https://i-blog.csdnimg.cn/direct/d41d40f128db420fb65766c134c217a8.png)
When the following interface appears, simply press the `Enter` key, and the board will reboot.
![Insert image description here](https://i-blog.csdnimg.cn/direct/d27f1e41e1e541338578add0ddee57c2.png)

## 2. Check Video Devices
```
ls /dev/video*
```
The image result shows two CSI cameras connected: typically, one CSI camera displays one `video` device.
![Insert image description here](https://i-blog.csdnimg.cn/direct/2b7b45be34ec43b0901f8b03dd3c918a.png)

## 3. Preview Camera Feed
Enter the following command in the terminal, and the system will automatically pop up a camera preview window (default opens `/dev/video0`):
```
nvgstcapture-1.0
```
![Insert image description here](https://i-blog.csdnimg.cn/direct/dc354a021a244057b858bd24ddf3cf12.png)
### 3.1. Specify Camera
If there are multiple cameras, you can specify the camera ID:
```
nvgstcapture-1.0 --sensor-id=1
```
![Insert image description here](https://i-blog.csdnimg.cn/direct/02dd8ba7d43e471f9f45031f789239db.png)
### 3.2. Specify Preview Resolution
If there is only one CSI camera, change `--sensor-id=1` to `--sensor-id=0`:
```
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```
![Insert image description here](https://i-blog.csdnimg.cn/direct/aaa929c305d645a8ad5ccc790cfba64e.png)
