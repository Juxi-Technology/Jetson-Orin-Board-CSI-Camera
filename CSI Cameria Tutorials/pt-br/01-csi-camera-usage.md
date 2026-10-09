[English](../en/01-csi-camera-usage.md) | [Deutsch](../de/01-csi-camera-usage.md) | [Español](../es/01-csi-camera-usage.md) | [Français](../fr/01-csi-camera-usage.md) | [Italiano](../it/01-csi-camera-usage.md) | [日本語](../ja/01-csi-camera-usage.md) | [한국어](../ko/01-csi-camera-usage.md) | Português (BR) | [Português (PT)](../pt-pt/01-csi-camera-usage.md) | [简体中文](../zh-hans/01-csi-camera-usage.md) | [繁體中文](../zh-hant/01-csi-camera-usage.md)

# 01. Uso da câmera CSI

## 1. Configurar os pinos da câmera CSI

```Plain Text
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![Screenshot from 2025\-07\-30 16\-42\-49\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

Use as setas para baixo para selecionar **Configure Jetson 24pin CSI Connector**. Em seguida, pressione Enter para entrar na próxima opção

![Screenshot from 2025\-07\-30 16\-42\-57\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

Selecione **Configure for compatible hardware** e, em seguida, pressione Enter.

![Screenshot from 2025\-07\-30 16\-43\-09\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

Use as setas para baixo para selecionar **Camera IMX219 Dual** e, em seguida, pressione Enter.

Se depois de reiniciar a visualização da imagem da câmera apresentar erro ou tela preta, altere aqui para Camera IMX219\-C

![Screenshot from 2025\-07\-30 16\-43\-19\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

Selecione **Save pin changes** e, em seguida, pressione Enter.

![Screenshot from 2025\-07\-30 16\-43\-34\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

Use as setas para baixo para selecionar **Save and reboot to reconfigure pins** e, em seguida, pressione Enter.

![Screenshot from 2025\-07\-30 16\-43\-53\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

Quando a interface abaixo aparecer, pressione diretamente a tecla Enter e a placa-mãe será reiniciada.

![Screenshot from 2025\-07\-30 16\-42\-57\.jpg](../en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

## 2. Verificar os dispositivos de vídeo

```Plain Text
ls /dev/video*
```

O resultado da imagem corresponde a duas câmeras CSI conectadas: normalmente uma câmera CSI exibe um dispositivo `video`

![Screenshot from 2025\-07\-30 16\-46\-33\.png](../en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

## 3. Pré-visualizar a imagem da câmera

Digite o comando abaixo no terminal e o sistema abrirá automaticamente a janela da imagem da câmera: por padrão, abre o dispositivo `/dev/video0`

```Plain Text
nvgstcapture-1.0
```

![Screenshot from 2025\-07\-30 16\-48\-44\.png](../en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

### 3\.1. Especificar a câmera

Se houver várias câmeras, é possível especificar o ID da câmera:

```Plain Text
nvgstcapture-1.0 --sensor-id=1
```

![Screenshot from 2025\-07\-30 16\-55\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

### 3\.2. Especificar a resolução de pré-visualização

Se houver apenas uma câmera CSI, pode alterar `--sensor-id=1` para `--sensor-id=0`:

```Plain Text
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![Screenshot from 2025\-07\-30 16\-59\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-59-24.png)



