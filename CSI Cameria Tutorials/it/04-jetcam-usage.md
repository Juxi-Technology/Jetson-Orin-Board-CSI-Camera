[English](../en/04-jetcam-usage.md) | [Deutsch](../de/04-jetcam-usage.md) | [Español](../es/04-jetcam-usage.md) | [Français](../fr/04-jetcam-usage.md) | Italiano | [日本語](../ja/04-jetcam-usage.md) | [한국어](../ko/04-jetcam-usage.md) | [Português (BR)](../pt-br/04-jetcam-usage.md) | [Português (PT)](../pt-pt/04-jetcam-usage.md) | [简体中文](../zh-hans/04-jetcam-usage.md) | [繁體中文](../zh-hant/04-jetcam-usage.md)

# 04. Uso di JetCam

Uso di JetCam

1. Installazione di JetCam

2. Uso di JetCam

2\.1. Fotocamera CSI

Spiegazione del codice principale

Chiamata alla fotocamera

Ottenere l'immagine della fotocamera

2\.1\.1. Fotocamera singola

2\.1\.2. Fotocamere multiple

2\.2. Fotocamera USB

Riferimenti



JetCam è una libreria Python facile da usare sviluppata da NVIDIA per la piattaforma Jetson, destinata a integrare e gestire fotocamere USB o fotocamere CSI

## 1. Installazione di JetCam

```Plain Text
git clone https://github.com/NVIDIA-AI-IOT/jetcam
cd jetcam
sudo python3 setup.py install
sudo pip3 install ipywidgets
```

## 2. Uso di JetCam

JetCam fornisce programmi di esempio tipici per mostrare all'utente la chiamata a fotocamere CSI e USB.

Gli esempi devono essere eseguiti con Jupyter Lab; utilizzando il nostro sistema di immagine di fabbrica, è possibile accedere direttamente tramite IP della scheda:8888!

### 2\.1. Fotocamera CSI

Nell'interfaccia web di Jupyter Lab, accedere alla cartella in cui si trova la fotocamera CSI e aprire la cartella corrispondente:

`/home/jetson/jetcam/notebooks/csi_camera`

**Nota: se non si ha familiarità con Jupyter Lab, è possibile consultare il tutorial sull'uso di Jupyter Lab per conoscere le operazioni di base!**

#### Spiegazione del codice principale

##### Chiamata alla fotocamera

width: larghezza di output dell'immagine

height: altezza di output dell'immagine

`from jetcam.csi_camera import CSICamera`

`camera = CSICamera(width=224, height=224)`

##### Ottenere l'immagine della fotocamera

`image = camera.read()`

#### 2\.1\.1. Fotocamera singola

> **Percorso del codice sorgente**
> 
> 

`/home/jetson/jetcam/notebooks/csi_camera/csi_camera.ipynb`

> **Risultato dell'esecuzione**
> 
> 

Dopo aver aperto il file di programma, eseguire le singole celle dall'alto verso il basso:

![Screenshot from 2025\-07\-31 15\-45\-33\.png](../en/images/Screenshot%20from%202025-07-31%2015-45-33.png)

#### 2\.1\.2. Fotocamere multiple

> **Percorso del codice sorgente**
> 
> 

`/home/jetson/jetcam/notebooks/csi_camera/multi_csi_camera.ipynb`

> **Risultato dell'esecuzione**
> 
> 

Dopo aver aperto il file di programma, eseguire le singole celle dall'alto verso il basso:

![Screenshot from 2025\-07\-31 15\-53\-42\.png](../en/images/Screenshot%20from%202025-07-31%2015-53-42.png)

### 2\.2. Fotocamera USB

In Jupyter Lab, accedere alla cartella in cui si trova la fotocamera USB e aprire il file; percorso della cartella nel sistema di immagine di fabbrica:

`/home/jetson/jetcam/notebooks/usb_camera`

![Screenshot from 2025\-07\-31 16\-08\-19\.png](../en/images/Screenshot%20from%202025-07-31%2016-08-19.png)

## Riferimenti

[https://github\.com/NVIDIA\-AI\-IOT/jetcam](https://github.com/NVIDIA-AI-IOT/jetcam)

