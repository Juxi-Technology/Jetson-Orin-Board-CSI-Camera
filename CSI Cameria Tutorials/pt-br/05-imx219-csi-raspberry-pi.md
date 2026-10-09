[English](../en/05-imx219-csi-raspberry-pi.md) | [Deutsch](../de/05-imx219-csi-raspberry-pi.md) | [Español](../es/05-imx219-csi-raspberry-pi.md) | [Français](../fr/05-imx219-csi-raspberry-pi.md) | [Italiano](../it/05-imx219-csi-raspberry-pi.md) | [日本語](../ja/05-imx219-csi-raspberry-pi.md) | [한국어](../ko/05-imx219-csi-raspberry-pi.md) | Português (BR) | [Português (PT)](../pt-pt/05-imx219-csi-raspberry-pi.md) | [简体中文](../zh-hans/05-imx219-csi-raspberry-pi.md) | [繁體中文](../zh-hant/05-imx219-csi-raspberry-pi.md)

# 05. Tutorial da câmera IMX219\-CSI (Raspberry Pi)

##### 1. Primeiro, use a instrução "ls" para verificar se existe o nó de dispositivo vchiq: insira ls /dev

![image\.png](../en/images/image%204.png)

Se não existir, pode ser que haja um problema no kernel ou no hardware do dispositivo; pode tentar reinstalar o sistema ou substituir o hardware.

##### 2. Execute o comando "sudo raspi\-config" para habilitar a câmera CSI do Raspberry Pi

![image\.png](../en/images/image.png)

![image\.png](../en/images/image%206.png)

![image\.png](../en/images/image%205.png)

![image\.png](../en/images/image%201.png)

Depois saia e insira o comando sudo reboot para reiniciar o Raspberry Pi

##### 3. Insira "vcgencmd get\_camera" para verificar se a câmera atual e a habilitação estão disponíveis

![image\.png](../en/images/image%203.png)

Se detected=0, significa que o módulo da câmera não está bem conectado; verifique novamente o hardware. detected=1 significa que a câmera CSI está conectada corretamente. supported=1 significa que a câmera já está habilitada e pode ser usada. supported=0 significa que a câmera CSI não está habilitada e é necessário habilitar o módulo da câmera.

## **3\. Tirar fotos com o comando rapistill**

Insira **"raspistill \-o image\.jpg"** e você conseguirá tirar e salvar a foto com sucesso; nesse momento a câmera acenderá uma luz vermelha. Para mais parâmetros, use raspistill \-\-help

![image\.png](../en/images/image%202.png)

Transfira a imagem image\.jpg para a área de trabalho do Windows e abra-a para ver o efeito da foto tirada



