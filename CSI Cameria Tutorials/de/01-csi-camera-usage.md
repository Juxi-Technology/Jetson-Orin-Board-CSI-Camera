[English](../en/01-csi-camera-usage.md) | Deutsch | [Español](../es/01-csi-camera-usage.md) | [Français](../fr/01-csi-camera-usage.md) | [Italiano](../it/01-csi-camera-usage.md) | [日本語](../ja/01-csi-camera-usage.md) | [한국어](../ko/01-csi-camera-usage.md) | [Português (BR)](../pt-br/01-csi-camera-usage.md) | [Português (PT)](../pt-pt/01-csi-camera-usage.md) | [简体中文](../zh-hans/01-csi-camera-usage.md) | [繁體中文](../zh-hant/01-csi-camera-usage.md)

# 01、CSI-Kamera verwenden

## 1、CSI-Kamera-Pins konfigurieren

```Plain Text
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![Screenshot from 2025\-07\-30 16\-42\-49\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

Wählen Sie mit der Pfeiltaste nach unten **Configure Jetson 24pin CSI Connector**. Drücken Sie dann Enter, um zur nächsten Option zu gelangen.

![Screenshot from 2025\-07\-30 16\-42\-57\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

Wählen Sie **Configure for compatible hardware** und drücken Sie dann Enter.

![Screenshot from 2025\-07\-30 16\-43\-09\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

Wählen Sie mit der Pfeiltaste nach unten **Camera IMX219 Dual** und drücken Sie dann Enter.

Falls nach dem anschließenden Neustart bei der Kameravorschau ein Fehler auftritt oder der Bildschirm schwarz bleibt, wählen Sie hier Camera IMX219\-C.

![Screenshot from 2025\-07\-30 16\-43\-19\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

Wählen Sie **Save pin changes** und drücken Sie dann Enter.

![Screenshot from 2025\-07\-30 16\-43\-34\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

Wählen Sie mit der Pfeiltaste nach unten **Save and reboot to reconfigure pins** und drücken Sie dann Enter.

![Screenshot from 2025\-07\-30 16\-43\-53\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

Wenn die folgende Oberfläche erscheint, drücken Sie direkt die Enter-Taste, die Hauptplatine wird neu gestartet.

![Screenshot from 2025\-07\-30 16\-42\-57\.jpg](../en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

## 2、Video-Geräte anzeigen

```Plain Text
ls /dev/video*
```

Das Ergebnis im Bild zeigt den Anschluss von zwei CSI-Kameras: Normalerweise wird für eine CSI-Kamera ein `video`-Gerät angezeigt.

![Screenshot from 2025\-07\-30 16\-46\-33\.png](../en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

## 3、Kamerabild in der Vorschau anzeigen

Geben Sie im Terminal den folgenden Befehl ein; das System öffnet automatisch ein Fenster mit dem Kamerabild: Standardmäßig wird das Gerät `/dev/video0` geöffnet.

```Plain Text
nvgstcapture-1.0
```

![Screenshot from 2025\-07\-30 16\-48\-44\.png](../en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

### 3\.1、Kamera festlegen

Bei mehreren Kameras können Sie die Kamera-ID festlegen:

```Plain Text
nvgstcapture-1.0 --sensor-id=1
```

![Screenshot from 2025\-07\-30 16\-55\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

### 3\.2、Vorschauauflösung festlegen

Wenn nur eine CSI-Kamera vorhanden ist, können Sie `--sensor-id=1` in `--sensor-id=0` ändern:

```Plain Text
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![Screenshot from 2025\-07\-30 16\-59\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-59-24.png)



