[English](../en/02-autofocus-camera-usage.md) | [Deutsch](../de/02-autofocus-camera-usage.md) | [Español](../es/02-autofocus-camera-usage.md) | [Français](../fr/02-autofocus-camera-usage.md) | [Italiano](../it/02-autofocus-camera-usage.md) | [日本語](../ja/02-autofocus-camera-usage.md) | [한국어](../ko/02-autofocus-camera-usage.md) | Português (BR) | [Português (PT)](../pt-pt/02-autofocus-camera-usage.md) | [简体中文](../zh-hans/02-autofocus-camera-usage.md) | [繁體中文](../zh-hant/02-autofocus-camera-usage.md)

# 02. Uso da câmera com foco automático

## 1. Verificar os dispositivos de vídeo

```Plain Text
ls /dev/video*
```

O resultado da imagem corresponde a duas câmeras CSI e uma câmera USB conectadas: normalmente uma câmera CSI exibe um dispositivo `video`, e uma câmera USB exibe dois dispositivos `video`; para a câmera USB, escolha o `/dev/video2`, recém-adicionado e de número menor, para chamar (ao conectar a câmera USB, o sistema adiciona os números de dispositivo `/dev/video2` e `/dev/video3`)

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

## 2. GUVCView

O GUVCView é um software de código aberto para o sistema Linux, usado para capturar e gravar vídeos e imagens, principalmente para webcams.

### 2\.1. Instalação do GUVCView

```Plain Text
sudo apt update
sudo apt install guvcview -y
```

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

### 2\.2. Uso do GUVCView

No menu de aplicações, clique no ícone `guvcview`, ou digite o comando de inicialização no terminal: escolha a câmera USB, pois a câmera CSI não tem imagem de visualização

```Plain Text
guvcview
```

![截图\_20250925170724\.png](../en/images/截图_20250925170724.png)

![Screenshot from 2025\-07\-30 17\-04\-00\.png](../en/images/Screenshot%20from%202025-07-30%2017-04-00.png)

## 3. VLC

O VLC media player é um reprodutor multimídia livre e de código aberto, que suporta vários formatos de áudio e vídeo, além de DVD, CD de áudio, VCD e vários protocolos de streaming.

### 3\.1. Instalação do VLC

```Plain Text
sudo apt update
sudo apt install vlc -y
```

![Screenshot from 2025\-07\-30 17\-05\-31\.png](../en/images/Screenshot%20from%202025-07-30%2017-05-31.png)

### 3\.2. Uso do VLC

No menu de aplicações, clique no ícone `VLC media player`, ou digite o comando de inicialização no terminal: escolha a câmera USB, pois a câmera CSI não tem imagem de visualização

```Plain Text
vlc
```

![Screenshot from 2025\-07\-30 17\-06\-32\.png](../en/images/Screenshot%20from%202025-07-30%2017-06-32.png)

![Screenshot from 2025\-07\-30 17\-07\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-07-09.png)

Selecione o número de dispositivo correspondente à câmera USB:

![截图\_20250925170820\.png](../en/images/截图_20250925170820.png)

![Screenshot from 2025\-07\-30 17\-08\-35\.png](../en/images/Screenshot%20from%202025-07-30%2017-08-35.png)



