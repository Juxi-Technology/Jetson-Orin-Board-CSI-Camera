[English](../en/05-imx219-csi-raspberry-pi.md) | [Deutsch](../de/05-imx219-csi-raspberry-pi.md) | [Español](../es/05-imx219-csi-raspberry-pi.md) | [Français](../fr/05-imx219-csi-raspberry-pi.md) | [Italiano](../it/05-imx219-csi-raspberry-pi.md) | [日本語](../ja/05-imx219-csi-raspberry-pi.md) | 한국어 | [Português (BR)](../pt-br/05-imx219-csi-raspberry-pi.md) | [Português (PT)](../pt-pt/05-imx219-csi-raspberry-pi.md) | [简体中文](../zh-hans/05-imx219-csi-raspberry-pi.md) | [繁體中文](../zh-hant/05-imx219-csi-raspberry-pi.md)

# 05, IMX219\-CSI 카메라 (Raspberry Pi) 튜토리얼

##### 1, 먼저 "ls" 명령어를 사용하여 vchiq 장치 노드가 존재하는지 확인합니다: ls /dev 입력

![image\.png](../en/images/image%204.png)

없는 경우 커널 또는 장치 하드웨어에 문제가 있을 수 있으므로 시스템을 다시 설치하거나 하드웨어를 교체해 보세요.

##### 2, "sudo raspi\-config" 명령어를 실행하여 Raspberry Pi CSI 카메라를 활성화합니다

![image\.png](../en/images/image.png)

![image\.png](../en/images/image%206.png)

![image\.png](../en/images/image%205.png)

![image\.png](../en/images/image%201.png)

그런 다음 종료하고 sudo reboot 명령어를 입력하여 Raspberry Pi를 재시작합니다

##### 3, "vcgencmd get\_camera"를 입력하여 현재 카메라와 활성화가 사용 가능한지 확인합니다

![image\.png](../en/images/image%203.png)

detected=0이면 카메라 모듈이 제대로 연결되지 않은 것이므로 하드웨어를 다시 점검하세요. detected=1이면 CSI 카메라 연결이 정상임을 의미합니다. supported=1은 카메라가 활성화되어 카메라를 사용할 수 있음을 의미합니다. supported=0이면 CSI 카메라가 활성화되지 않은 것이므로 카메라 모듈을 활성화해야 합니다.

## **3\.rapistill 명령어로 사진 촬영**

**"raspistill \-o image\.jpg"**를 입력하면 사진 촬영과 저장에 성공하며, 이때 카메라의 빨간 램프가 켜집니다. 더 많은 매개변수는 raspistill \-\-help를 사용하세요

![image\.png](../en/images/image%202.png)

image\.jpg 이미지를 Windows 데스크톱으로 전송하여 열면, 촬영된 결과를 확인할 수 있습니다



