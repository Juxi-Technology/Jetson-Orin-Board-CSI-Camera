[English](../en/01-csi-camera-usage.md) | [Deutsch](../de/01-csi-camera-usage.md) | Español | [Français](../fr/01-csi-camera-usage.md) | [Italiano](../it/01-csi-camera-usage.md) | [日本語](../ja/01-csi-camera-usage.md) | [한국어](../ko/01-csi-camera-usage.md) | [Português (BR)](../pt-br/01-csi-camera-usage.md) | [Português (PT)](../pt-pt/01-csi-camera-usage.md) | [简体中文](../zh-hans/01-csi-camera-usage.md) | [繁體中文](../zh-hant/01-csi-camera-usage.md)

# 01. Uso de la cámara CSI

## 1. Configurar los pines de la cámara CSI

```Plain Text
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![Screenshot from 2025\-07\-30 16\-42\-49\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

Pulse la tecla de flecha abajo para seleccionar **Configure Jetson 24pin CSI Connector**. A continuación, pulse Enter para pasar a la siguiente opción

![Screenshot from 2025\-07\-30 16\-42\-57\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

Seleccione **Configure for compatible hardware** y, a continuación, pulse Enter.

![Screenshot from 2025\-07\-30 16\-43\-09\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

Pulse la tecla de flecha abajo para seleccionar **Camera IMX219 Dual** y, a continuación, pulse Enter.

Si después de reiniciar aparece un error o una pantalla negra al ejecutar la previsualización de la cámara, cambie aquí a Camera IMX219\-C

![Screenshot from 2025\-07\-30 16\-43\-19\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

Seleccione **Save pin changes** y, a continuación, pulse Enter.

![Screenshot from 2025\-07\-30 16\-43\-34\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

Pulse la tecla de flecha abajo para seleccionar **Save and reboot to reconfigure pins** y, a continuación, pulse Enter.

![Screenshot from 2025\-07\-30 16\-43\-53\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

Cuando aparezca la siguiente interfaz, pulse directamente la tecla Enter y la placa se reiniciará.

![Screenshot from 2025\-07\-30 16\-42\-57\.jpg](../en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

## 2. Ver el dispositivo de vídeo

```Plain Text
ls /dev/video*
```

El resultado de la imagen corresponde a dos cámaras CSI conectadas: normalmente una cámara CSI muestra un dispositivo `video`

![Screenshot from 2025\-07\-30 16\-46\-33\.png](../en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

## 3. Previsualizar la imagen de la cámara

Introduzca el siguiente comando en el terminal y el sistema abrirá automáticamente la ventana de imagen de la cámara: de forma predeterminada abre el dispositivo `/dev/video0`

```Plain Text
nvgstcapture-1.0
```

![Screenshot from 2025\-07\-30 16\-48\-44\.png](../en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

### 3\.1. Especificar la cámara

Si hay varias cámaras, puede especificar el ID de la cámara:

```Plain Text
nvgstcapture-1.0 --sensor-id=1
```

![Screenshot from 2025\-07\-30 16\-55\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

### 3\.2. Especificar la resolución de previsualización

Si solo hay una cámara CSI, puede cambiar `--sensor-id=1` por `--sensor-id=0`:

```Plain Text
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![Screenshot from 2025\-07\-30 16\-59\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-59-24.png)



