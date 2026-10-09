[English](../en/04-jetcam-usage.md) | [Deutsch](../de/04-jetcam-usage.md) | [Español](../es/04-jetcam-usage.md) | [Français](../fr/04-jetcam-usage.md) | [Italiano](../it/04-jetcam-usage.md) | [日本語](../ja/04-jetcam-usage.md) | [한국어](../ko/04-jetcam-usage.md) | Português (BR) | [Português (PT)](../pt-pt/04-jetcam-usage.md) | [简体中文](../zh-hans/04-jetcam-usage.md) | [繁體中文](../zh-hant/04-jetcam-usage.md)

# 04. Uso do JetCam

Uso do JetCam

1. Instalação do JetCam

2. Uso do JetCam

2\.1. Câmera CSI

Explicação do código principal

Chamar a câmera

Obter a imagem da câmera

2\.1\.1. Câmera única

2\.1\.2. Várias câmeras

2\.2. Câmera USB

Referências



JetCam é uma biblioteca Python de fácil uso desenvolvida pela NVIDIA para a plataforma Jetson, usada para integrar e operar câmeras USB ou câmeras CSI

## 1. Instalação do JetCam

```Plain Text
git clone https://github.com/NVIDIA-AI-IOT/jetcam
cd jetcam
sudo python3 setup.py install
sudo pip3 install ipywidgets
```

## 2. Uso do JetCam

O JetCam fornece programas de exemplo típicos para demonstrar ao usuário a chamada das câmeras CSI e USB.

Os exemplos precisam ser executados com o Jupyter Lab; usando o nosso sistema de imagem de fábrica, é possível acessar diretamente através de IP da placa-mãe:8888!

### 2\.1. Câmera CSI

No Jupyter Lab (interface web), entre na pasta onde está a câmera CSI e abra a pasta correspondente:

`/home/jetson/jetcam/notebooks/csi_camera`

**Atenção: quem não estiver familiarizado com o Jupyter Lab pode consultar o tutorial de uso do Jupyter Lab para conhecer as operações básicas!**

#### Explicação do código principal

##### Chamar a câmera

width: largura de saída da imagem

height: altura de saída da imagem

`from jetcam.csi_camera import CSICamera`

`camera = CSICamera(width=224, height=224)`

##### Obter a imagem da câmera

`image = camera.read()`

#### 2\.1\.1. Câmera única

> **Caminho do código-fonte**
> 
> 

`/home/jetson/jetcam/notebooks/csi_camera/csi_camera.ipynb`

> **Comportamento em execução**
> 
> 

Após abrir o arquivo do programa, execute as células uma a uma, de cima para baixo:

![Screenshot from 2025\-07\-31 15\-45\-33\.png](../en/images/Screenshot%20from%202025-07-31%2015-45-33.png)

#### 2\.1\.2. Várias câmeras

> **Caminho do código-fonte**
> 
> 

`/home/jetson/jetcam/notebooks/csi_camera/multi_csi_camera.ipynb`

> **Comportamento em execução**
> 
> 

Após abrir o arquivo do programa, execute as células uma a uma, de cima para baixo:

![Screenshot from 2025\-07\-31 15\-53\-42\.png](../en/images/Screenshot%20from%202025-07-31%2015-53-42.png)

### 2\.2. Câmera USB

No Jupyter Lab, entre na pasta onde está a câmera USB e abra o arquivo; caminho da pasta no sistema de imagem de fábrica:

`/home/jetson/jetcam/notebooks/usb_camera`

![Screenshot from 2025\-07\-31 16\-08\-19\.png](../en/images/Screenshot%20from%202025-07-31%2016-08-19.png)

## Referências

[https://github\.com/NVIDIA\-AI\-IOT/jetcam](https://github.com/NVIDIA-AI-IOT/jetcam)

