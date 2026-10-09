[English](../en/01-csi-camera-usage.md) | [Deutsch](../de/01-csi-camera-usage.md) | [Español](../es/01-csi-camera-usage.md) | [Français](../fr/01-csi-camera-usage.md) | [Italiano](../it/01-csi-camera-usage.md) | [日本語](../ja/01-csi-camera-usage.md) | 한국어 | [Português (BR)](../pt-br/01-csi-camera-usage.md) | [Português (PT)](../pt-pt/01-csi-camera-usage.md) | [简体中文](../zh-hans/01-csi-camera-usage.md) | [繁體中文](../zh-hant/01-csi-camera-usage.md)

# 01, CSI 카메라 사용

## 1, CSI 카메라 핀 설정

```Plain Text
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![Screenshot from 2025\-07\-30 16\-42\-49\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

방향키 아래로 **Configure Jetson 24pin CSI Connector**를 선택합니다. 그런 다음 Enter를 눌러 다음 옵션으로 이동합니다

![Screenshot from 2025\-07\-30 16\-42\-57\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

**Configure for compatible hardware** 를 선택한 후 Enter를 누릅니다.

![Screenshot from 2025\-07\-30 16\-43\-09\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

방향키 아래로 **Camera IMX219 Dual**를 선택한 후 Enter를 누릅니다.

나중에 재부팅한 후 카메라 미리보기 화면을 실행했을 때 오류가 발생하거나 검은 화면이 나오면 여기서 Camera IMX219\-C로 변경합니다

![Screenshot from 2025\-07\-30 16\-43\-19\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

**Save pin changes** 를 선택한 후 Enter를 누릅니다.

![Screenshot from 2025\-07\-30 16\-43\-34\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

방향키 아래로 **Save and reboot to reconfigure pins**를 선택한 후 Enter를 누릅니다.

![Screenshot from 2025\-07\-30 16\-43\-53\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

다음 화면이 나타나면 바로 Enter 키를 누르면 메인보드가 재시작됩니다.

![Screenshot from 2025\-07\-30 16\-42\-57\.jpg](../en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

## 2, video 장치 확인

```Plain Text
ls /dev/video*
```

그림의 결과는 CSI 카메라 2개를 연결한 결과입니다: 일반적으로 CSI 카메라 1개당 `video` 장치 1개가 표시됩니다

![Screenshot from 2025\-07\-30 16\-46\-33\.png](../en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

## 3, 카메라 화면 미리보기

터미널에 아래 명령어를 입력하면 시스템이 자동으로 카메라 화면 창을 띄웁니다: 기본적으로 `/dev/video0` 장치를 엽니다

```Plain Text
nvgstcapture-1.0
```

![Screenshot from 2025\-07\-30 16\-48\-44\.png](../en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

### 3\.1, 카메라 지정

카메라가 여러 개인 경우 카메라 ID를 지정할 수 있습니다:

```Plain Text
nvgstcapture-1.0 --sensor-id=1
```

![Screenshot from 2025\-07\-30 16\-55\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

### 3\.2, 미리보기 해상도 지정

CSI 카메라가 하나뿐인 경우 `--sensor-id=1`을 `--sensor-id=0`으로 변경할 수 있습니다:

```Plain Text
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![Screenshot from 2025\-07\-30 16\-59\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-59-24.png)



