[English](../en/05-imx219-csi-raspberry-pi.md) | [Deutsch](../de/05-imx219-csi-raspberry-pi.md) | [Español](../es/05-imx219-csi-raspberry-pi.md) | [Français](../fr/05-imx219-csi-raspberry-pi.md) | Italiano | [日本語](../ja/05-imx219-csi-raspberry-pi.md) | [한국어](../ko/05-imx219-csi-raspberry-pi.md) | [Português (BR)](../pt-br/05-imx219-csi-raspberry-pi.md) | [Português (PT)](../pt-pt/05-imx219-csi-raspberry-pi.md) | [简体中文](../zh-hans/05-imx219-csi-raspberry-pi.md) | [繁體中文](../zh-hant/05-imx219-csi-raspberry-pi.md)

# 05. Tutorial della fotocamera IMX219\-CSI (Raspberry Pi)

##### 1. Innanzitutto, utilizzare il comando "ls" per verificare se esiste il nodo di dispositivo vchiq: digitare ls /dev

![image\.png](../en/images/image%204.png)

Se non esiste, potrebbe trattarsi di un problema del kernel o dell'hardware del dispositivo; è possibile provare a riscrivere il sistema o a sostituire l'hardware.

##### 2. Eseguire il comando "sudo raspi\-config" per abilitare la fotocamera CSI del Raspberry Pi

![image\.png](../en/images/image.png)

![image\.png](../en/images/image%206.png)

![image\.png](../en/images/image%205.png)

![image\.png](../en/images/image%201.png)

Quindi uscire e digitare il comando sudo reboot per riavviare il Raspberry Pi

##### 3. Digitare "vcgencmd get\_camera" per verificare se la fotocamera attuale e la sua abilitazione sono disponibili

![image\.png](../en/images/image%203.png)

Se detected=0, significa che il modulo fotocamera non è collegato correttamente; controllare nuovamente l'hardware. detected=1 indica che la fotocamera CSI è collegata correttamente. supported=1 indica che la fotocamera è già abilitata e può essere utilizzata. supported=0 indica che la fotocamera CSI non è abilitata ed è necessario abilitare il modulo fotocamera.

## **3\. Scattare foto con il comando rapistill**

Digitare **"raspistill \-o image\.jpg"** per scattare e salvare la foto correttamente; in quel momento la fotocamera accende una luce rossa. Per ulteriori parametri, utilizzare raspistill \-\-help

![image\.png](../en/images/image%202.png)

Trasferire l'immagine image\.jpg sul desktop di Windows e aprirla per vedere il risultato della foto



