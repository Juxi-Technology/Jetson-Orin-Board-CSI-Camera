[English](../en/02-autofocus-camera-usage.md) | [Deutsch](../de/02-autofocus-camera-usage.md) | Español | [Français](../fr/02-autofocus-camera-usage.md) | [Italiano](../it/02-autofocus-camera-usage.md) | [日本語](../ja/02-autofocus-camera-usage.md) | [한국어](../ko/02-autofocus-camera-usage.md) | [Português (BR)](../pt-br/02-autofocus-camera-usage.md) | [Português (PT)](../pt-pt/02-autofocus-camera-usage.md) | [简体中文](../zh-hans/02-autofocus-camera-usage.md) | [繁體中文](../zh-hant/02-autofocus-camera-usage.md)

# 02. Uso de la cámara con enfoque automático

## 1. Ver el dispositivo de vídeo

```Plain Text
ls /dev/video*
```

El resultado de la imagen corresponde a dos cámaras CSI y una cámara USB conectadas: normalmente una cámara CSI muestra un dispositivo `video`, una cámara USB muestra dos dispositivos `video`, y para la cámara USB se selecciona el `/dev/video2` recién añadido y de número menor (al conectar la cámara USB el sistema añade los números de dispositivo `/dev/video2` y `/dev/video3`)

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

## 2. GUVCView

GUVCView es un software de código abierto para sistemas Linux, utilizado para capturar y grabar vídeo e imágenes, principalmente para cámaras web.

### 2\.1. Instalación de GUVCView

```Plain Text
sudo apt update
sudo apt install guvcview -y
```

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

### 2\.2. Uso de GUVCView

Acceda a la barra de menú de aplicaciones y haga clic en el icono `guvcview`, o introduzca el comando de inicio en el terminal: seleccione la cámara USB; la cámara CSI no muestra imagen de previsualización

```Plain Text
guvcview
```

![截图\_20250925170724\.png](../en/images/截图_20250925170724.png)

![Screenshot from 2025\-07\-30 17\-04\-00\.png](../en/images/Screenshot%20from%202025-07-30%2017-04-00.png)

## 3. VLC

VLC media player es un reproductor multimedia libre y de código abierto que admite diversos formatos de audio y vídeo, así como DVD, CD de audio, VCD y varios protocolos de transmisión multimedia.

### 3\.1. Instalación de VLC

```Plain Text
sudo apt update
sudo apt install vlc -y
```

![Screenshot from 2025\-07\-30 17\-05\-31\.png](../en/images/Screenshot%20from%202025-07-30%2017-05-31.png)

### 3\.2. Uso de VLC

Acceda a la barra de menú de aplicaciones y haga clic en el icono `VLC media player`, o introduzca el comando de inicio en el terminal: seleccione la cámara USB; la cámara CSI no muestra imagen de previsualización

```Plain Text
vlc
```

![Screenshot from 2025\-07\-30 17\-06\-32\.png](../en/images/Screenshot%20from%202025-07-30%2017-06-32.png)

![Screenshot from 2025\-07\-30 17\-07\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-07-09.png)

Seleccione el número de dispositivo correspondiente a la cámara USB:

![截图\_20250925170820\.png](../en/images/截图_20250925170820.png)

![Screenshot from 2025\-07\-30 17\-08\-35\.png](../en/images/Screenshot%20from%202025-07-30%2017-08-35.png)



