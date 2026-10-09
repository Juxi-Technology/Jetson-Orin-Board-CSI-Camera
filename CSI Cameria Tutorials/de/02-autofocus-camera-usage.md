[English](../en/02-autofocus-camera-usage.md) | Deutsch | [Español](../es/02-autofocus-camera-usage.md) | [Français](../fr/02-autofocus-camera-usage.md) | [Italiano](../it/02-autofocus-camera-usage.md) | [日本語](../ja/02-autofocus-camera-usage.md) | [한국어](../ko/02-autofocus-camera-usage.md) | [Português (BR)](../pt-br/02-autofocus-camera-usage.md) | [Português (PT)](../pt-pt/02-autofocus-camera-usage.md) | [简体中文](../zh-hans/02-autofocus-camera-usage.md) | [繁體中文](../zh-hant/02-autofocus-camera-usage.md)

# 02、Autofokus-Kamera verwenden

## 1、Video-Geräte anzeigen

```Plain Text
ls /dev/video*
```

Das Ergebnis im Bild zeigt den Anschluss von zwei CSI-Kameras und einer USB-Kamera: Normalerweise wird für eine CSI-Kamera ein `video`-Gerät und für eine USB-Kamera zwei `video`-Geräte angezeigt. Bei der USB-Kamera wählen Sie das neu hinzugefügte `/dev/video2` mit der kleineren Nummer (beim Anschließen der USB-Kamera fügt das System die Gerätenummern `/dev/video2` und `/dev/video3` hinzu).

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

## 2、GUVCView

GUVCView ist eine Open-Source-Software für Linux-Systeme zum Erfassen und Aufzeichnen von Videos und Bildern, die hauptsächlich für Webcam-Kameras verwendet wird.

### 2\.1、GUVCView installieren

```Plain Text
sudo apt update
sudo apt install guvcview -y
```

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

### 2\.2、GUVCView verwenden

Öffnen Sie die Anwendungsmenüleiste und klicken Sie auf das Symbol `guvcview`, oder geben Sie den Startbefehl im Terminal ein: Wählen Sie die USB-Kamera; die CSI-Kamera hat kein Vorschaubild.

```Plain Text
guvcview
```

![截图\_20250925170724\.png](../en/images/截图_20250925170724.png)

![Screenshot from 2025\-07\-30 17\-04\-00\.png](../en/images/Screenshot%20from%202025-07-30%2017-04-00.png)

## 3、VLC

VLC media player ist ein freier und quelloffener Multimedia-Player, der zahlreiche Audio- und Videoformate sowie DVD, Audio-CD, VCD und verschiedene Streaming-Protokolle unterstützt.

### 3\.1、VLC installieren

```Plain Text
sudo apt update
sudo apt install vlc -y
```

![Screenshot from 2025\-07\-30 17\-05\-31\.png](../en/images/Screenshot%20from%202025-07-30%2017-05-31.png)

### 3\.2、VLC verwenden

Öffnen Sie die Anwendungsmenüleiste und klicken Sie auf das Symbol `VLC media player`, oder geben Sie den Startbefehl im Terminal ein: Wählen Sie die USB-Kamera; die CSI-Kamera hat kein Vorschaubild.

```Plain Text
vlc
```

![Screenshot from 2025\-07\-30 17\-06\-32\.png](../en/images/Screenshot%20from%202025-07-30%2017-06-32.png)

![Screenshot from 2025\-07\-30 17\-07\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-07-09.png)

Wählen Sie die entsprechende Gerätenummer der USB-Kamera:

![截图\_20250925170820\.png](../en/images/截图_20250925170820.png)

![Screenshot from 2025\-07\-30 17\-08\-35\.png](../en/images/Screenshot%20from%202025-07-30%2017-08-35.png)



