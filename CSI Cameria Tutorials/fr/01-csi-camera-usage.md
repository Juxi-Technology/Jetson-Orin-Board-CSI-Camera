[English](../en/01-csi-camera-usage.md) | [Deutsch](../de/01-csi-camera-usage.md) | [Español](../es/01-csi-camera-usage.md) | Français | [Italiano](../it/01-csi-camera-usage.md) | [日本語](../ja/01-csi-camera-usage.md) | [한국어](../ko/01-csi-camera-usage.md) | [Português (BR)](../pt-br/01-csi-camera-usage.md) | [Português (PT)](../pt-pt/01-csi-camera-usage.md) | [简体中文](../zh-hans/01-csi-camera-usage.md) | [繁體中文](../zh-hant/01-csi-camera-usage.md)

# 01、Utilisation de la caméra CSI

## 1、Configurer les broches de la caméra CSI

```Plain Text
sudo /opt/nvidia/jetson-io/jetson-io.py
```

![Screenshot from 2025\-07\-30 16\-42\-49\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-49.png)

Utilisez la flèche bas pour sélectionner **Configure Jetson 24pin CSI Connector**. Appuyez ensuite sur Entrée pour passer à l'option suivante.

![Screenshot from 2025\-07\-30 16\-42\-57\.png](../en/images/Screenshot%20from%202025-07-30%2016-42-57.png)

Sélectionnez **Configure for compatible hardware**, puis appuyez sur Entrée.

![Screenshot from 2025\-07\-30 16\-43\-09\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-09.png)

Utilisez la flèche bas pour sélectionner **Camera IMX219 Dual**, puis appuyez sur Entrée.

Si, après le redémarrage, l'aperçu de la caméra affiche une erreur ou un écran noir, choisissez ici Camera IMX219\-C.

![Screenshot from 2025\-07\-30 16\-43\-19\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-19.png)

Sélectionnez **Save pin changes**, puis appuyez sur Entrée.

![Screenshot from 2025\-07\-30 16\-43\-34\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-34.png)

Utilisez la flèche bas pour sélectionner **Save and reboot to reconfigure pins**, puis appuyez sur Entrée.

![Screenshot from 2025\-07\-30 16\-43\-53\.png](../en/images/Screenshot%20from%202025-07-30%2016-43-53.png)

Lorsque l'interface suivante apparaît, appuyez directement sur la touche Entrée, la carte mère redémarre.

![Screenshot from 2025\-07\-30 16\-42\-57\.jpg](../en/images/Screenshot%20from%202025-07-30%2016-42-57.jpg)

## 2、Afficher les périphériques vidéo

```Plain Text
ls /dev/video*
```

L'image montre le résultat de la connexion de deux caméras CSI : en général, une caméra CSI affiche un périphérique `video`.

![Screenshot from 2025\-07\-30 16\-46\-33\.png](../en/images/Screenshot%20from%202025-07-30%2016-46-33.png)

## 3、Afficher l'image de la caméra en aperçu

Saisissez la commande suivante dans le terminal ; le système ouvre automatiquement une fenêtre avec l'image de la caméra : par défaut, le périphérique `/dev/video0` est ouvert.

```Plain Text
nvgstcapture-1.0
```

![Screenshot from 2025\-07\-30 16\-48\-44\.png](../en/images/Screenshot%20from%202025-07-30%2016-48-44.png)

### 3\.1、Spécifier la caméra

Si plusieurs caméras sont présentes, vous pouvez spécifier l'ID de la caméra :

```Plain Text
nvgstcapture-1.0 --sensor-id=1
```

![Screenshot from 2025\-07\-30 16\-55\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-55-24.png)

### 3\.2、Spécifier la résolution d'aperçu

Si une seule caméra CSI est présente, vous pouvez remplacer `--sensor-id=1` par `--sensor-id=0` :

```Plain Text
nvgstcapture-1.0 --sensor-id=1 --cus-prev-res=1280x720
```

![Screenshot from 2025\-07\-30 16\-59\-24\.png](../en/images/Screenshot%20from%202025-07-30%2016-59-24.png)



