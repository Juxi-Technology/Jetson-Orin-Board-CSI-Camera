[English](../en/05-imx219-csi-raspberry-pi.md) | Deutsch | [Español](../es/05-imx219-csi-raspberry-pi.md) | [Français](../fr/05-imx219-csi-raspberry-pi.md) | [Italiano](../it/05-imx219-csi-raspberry-pi.md) | [日本語](../ja/05-imx219-csi-raspberry-pi.md) | [한국어](../ko/05-imx219-csi-raspberry-pi.md) | [Português (BR)](../pt-br/05-imx219-csi-raspberry-pi.md) | [Português (PT)](../pt-pt/05-imx219-csi-raspberry-pi.md) | [简体中文](../zh-hans/05-imx219-csi-raspberry-pi.md) | [繁體中文](../zh-hant/05-imx219-csi-raspberry-pi.md)

# 05、IMX219\-CSI-Kamera (Raspberry Pi) Anleitung

##### 1、Verwenden Sie zunächst den Befehl "ls", um zu prüfen, ob ein vchiq-Geräteknoten vorhanden ist: geben Sie ls /dev ein

![image\.png](../en/images/image%204.png)

Wenn nicht, liegt möglicherweise ein Problem mit dem Kernel oder der Gerätehardware vor; versuchen Sie, das System neu zu flashen oder die Hardware auszutauschen.

##### 2、Führen Sie den Befehl "sudo raspi\-config" aus, um die CSI-Kamera des Raspberry Pi zu aktivieren

![image\.png](../en/images/image.png)

![image\.png](../en/images/image%206.png)

![image\.png](../en/images/image%205.png)

![image\.png](../en/images/image%201.png)

Beenden Sie dann und geben Sie den Befehl sudo reboot ein, um den Raspberry Pi neu zu starten

##### 3、Geben Sie "vcgencmd get\_camera" ein, um zu prüfen, ob die aktuelle Kamera und deren Aktivierung verfügbar sind

![image\.png](../en/images/image%203.png)

Wenn detected=0, ist das Kameramodul nicht richtig angeschlossen; überprüfen Sie die Hardware erneut. detected=1 bedeutet, dass die CSI-Kamera korrekt angeschlossen ist. supported=1 bedeutet, dass die Kamera aktiviert ist und verwendet werden kann. supported=0 bedeutet, dass die CSI-Kamera nicht aktiviert ist und das Kameramodul aktiviert werden muss.

## **3\.Verwenden Sie den rapistill-Befehl, um ein Foto aufzunehmen**

Geben Sie **"raspistill \-o image\.jpg"** ein, um erfolgreich ein Foto aufzunehmen und zu speichern; dabei leuchtet die Kamera rot. Weitere Parameter finden Sie mit raspistill \-\-help

![image\.png](../en/images/image%202.png)

Übertragen Sie das Bild image\.jpg auf den Windows-Desktop und öffnen Sie es, um das Ergebnis der Aufnahme zu sehen



