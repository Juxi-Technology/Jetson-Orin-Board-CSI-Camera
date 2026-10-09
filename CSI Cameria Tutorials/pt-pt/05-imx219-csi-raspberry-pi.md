[English](../en/05-imx219-csi-raspberry-pi.md) | [Deutsch](../de/05-imx219-csi-raspberry-pi.md) | [Español](../es/05-imx219-csi-raspberry-pi.md) | [Français](../fr/05-imx219-csi-raspberry-pi.md) | [Italiano](../it/05-imx219-csi-raspberry-pi.md) | [日本語](../ja/05-imx219-csi-raspberry-pi.md) | [한국어](../ko/05-imx219-csi-raspberry-pi.md) | [Português (BR)](../pt-br/05-imx219-csi-raspberry-pi.md) | Português (PT) | [简体中文](../zh-hans/05-imx219-csi-raspberry-pi.md) | [繁體中文](../zh-hant/05-imx219-csi-raspberry-pi.md)

# 05. Tutorial da câmara IMX219\-CSI (Raspberry Pi)

##### 1. Primeiro, utilize a instrução "ls" para verificar se existe o nó de dispositivo vchiq: introduza ls /dev

![image\.png](../en/images/image%204.png)

Se não existir, pode ser que haja um problema no kernel ou no hardware do dispositivo; pode tentar reinstalar o sistema ou substituir o hardware.

##### 2. Execute o comando "sudo raspi\-config" para ativar a câmara CSI do Raspberry Pi

![image\.png](../en/images/image.png)

![image\.png](../en/images/image%206.png)

![image\.png](../en/images/image%205.png)

![image\.png](../en/images/image%201.png)

Depois saia e introduza o comando sudo reboot para reiniciar o Raspberry Pi

##### 3. Introduza "vcgencmd get\_camera" para verificar se a câmara atual e a ativação estão disponíveis

![image\.png](../en/images/image%203.png)

Se detected=0, significa que o módulo da câmara não está bem ligado; verifique novamente o hardware. detected=1 significa que a câmara CSI está ligada corretamente. supported=1 significa que a câmara já está ativada e pode ser utilizada. supported=0 significa que a câmara CSI não está ativada e é necessário ativar o módulo da câmara.

## **3\. Tirar fotografias com o comando rapistill**

Introduza **"raspistill \-o image\.jpg"** e conseguirá tirar e guardar a fotografia com sucesso; nesse momento a câmara acenderá uma luz vermelha. Para mais parâmetros, utilize raspistill \-\-help

![image\.png](../en/images/image%202.png)

Transfira a imagem image\.jpg para o ambiente de trabalho do Windows e abra-a para ver o efeito da fotografia tirada



