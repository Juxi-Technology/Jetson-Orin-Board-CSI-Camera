[English](../en/01-csi-camera-usage.md) | [Deutsch](../de/01-csi-camera-usage.md) | [Español](../es/01-csi-camera-usage.md) | [Français](../fr/01-csi-camera-usage.md) | Italiano | [日本語](../ja/01-csi-camera-usage.md) | [한국어](../ko/01-csi-camera-usage.md) | [Português (BR)](../pt-br/01-csi-camera-usage.md) | [Português (PT)](../pt-pt/01-csi-camera-usage.md) | [简体中文](../zh-hans/01-csi-camera-usage.md) | [繁體中文](../zh-hant/01-csi-camera-usage.md)

# 01. Uso della fotocamera CSI

## 1. Configurazione dei pin della fotocamera CSI

```Plain Text
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![Screenshot from 2025\-07\-30 16\-42\-49\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

Premere il tasto freccia giù per selezionare **Configure Jetson 24pin CSI Connector**. Quindi premere Enter per passare all'opzione successiva

![Screenshot from 2025\-07\-30 16\-42\-57\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

Selezionare **Configure for compatible hardware**, quindi premere Enter.

![Screenshot from 2025\-07\-30 16\-43\-09\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

Premere il tasto freccia giù per selezionare **Camera IMX219 Dual**, quindi premere Enter.

Se dopo il riavvio la previsualizzazione della fotocamera mostra un errore o una schermata nera, modificare qui in Camera IMX219\-C

![Screenshot from 2025\-07\-30 16\-43\-19\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

Selezionare **Save pin changes**, quindi premere Enter.

![Screenshot from 2025\-07\-30 16\-43\-34\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

Premere il tasto freccia giù per selezionare **Save and reboot to reconfigure pins**, quindi premere Enter.

![Screenshot from 2025\-07\-30 16\-43\-53\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

Quando appare la seguente schermata, premere direttamente il tasto Enter e la scheda si riavvierà.

![Screenshot from 2025\-07\-30 16\-42\-57\.jpg](../en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

## 2. Visualizzare il dispositivo video

```Plain Text
ls /dev/video*
```

Il risultato dell'immagine corrisponde a due fotocamere CSI collegate: di norma una fotocamera CSI mostra un dispositivo `video`

![Screenshot from 2025\-07\-30 16\-46\-33\.png](../en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

## 3. Anteprima dell'immagine della fotocamera

Digitare il seguente comando nel terminale e il sistema aprirà automaticamente la finestra dell'immagine della fotocamera: per impostazione predefinita apre il dispositivo `/dev/video0`

```Plain Text
nvgstcapture-1.0
```

![Screenshot from 2025\-07\-30 16\-48\-44\.png](../en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

### 3\.1. Specificare la fotocamera

Se sono presenti più fotocamere, è possibile specificare l'ID della fotocamera:

```Plain Text
nvgstcapture-1.0 --sensor-id=1
```

![Screenshot from 2025\-07\-30 16\-55\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

### 3\.2. Specificare la risoluzione di anteprima

Se è presente una sola fotocamera CSI, è possibile cambiare `--sensor-id=1` in `--sensor-id=0`:

```Plain Text
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![Screenshot from 2025\-07\-30 16\-59\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-59-24.png)



