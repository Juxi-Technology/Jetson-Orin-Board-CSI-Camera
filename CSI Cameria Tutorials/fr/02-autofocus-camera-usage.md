[English](../en/02-autofocus-camera-usage.md) | [Deutsch](../de/02-autofocus-camera-usage.md) | [Español](../es/02-autofocus-camera-usage.md) | Français | [Italiano](../it/02-autofocus-camera-usage.md) | [日本語](../ja/02-autofocus-camera-usage.md) | [한국어](../ko/02-autofocus-camera-usage.md) | [Português (BR)](../pt-br/02-autofocus-camera-usage.md) | [Português (PT)](../pt-pt/02-autofocus-camera-usage.md) | [简体中文](../zh-hans/02-autofocus-camera-usage.md) | [繁體中文](../zh-hant/02-autofocus-camera-usage.md)

# 02、Utilisation de la caméra autofocus

## 1、Afficher les périphériques vidéo

```Plain Text
ls /dev/video*
```

L'image montre le résultat de la connexion de deux caméras CSI et d'une caméra USB : en général, une caméra CSI affiche un périphérique `video` et une caméra USB affiche deux périphériques `video`. Pour la caméra USB, sélectionnez le `/dev/video2` nouvellement ajouté et dont le numéro est plus petit (lors du branchement de la caméra USB, le système ajoute les numéros de périphérique `/dev/video2` et `/dev/video3`).

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

## 2、GUVCView

GUVCView est un logiciel libre et open source destiné aux systèmes Linux, utilisé pour capturer et enregistrer des vidéos et des images, principalement pour les caméras Webcam.

### 2\.1、Installer GUVCView

```Plain Text
sudo apt update
sudo apt install guvcview -y
```

![Screenshot from 2025\-07\-30 17\-01\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-01-09.png)

### 2\.2、Utiliser GUVCView

Ouvrez la barre de menus des applications et cliquez sur l'icône `guvcview`, ou saisissez la commande de démarrage dans le terminal : sélectionnez la caméra USB, la caméra CSI n'affiche aucun aperçu.

```Plain Text
guvcview
```

![截图\_20250925170724\.png](../en/images/截图_20250925170724.png)

![Screenshot from 2025\-07\-30 17\-04\-00\.png](../en/images/Screenshot%20from%202025-07-30%2017-04-00.png)

## 3、VLC

VLC media player est un lecteur multimédia libre et open source qui prend en charge de nombreux formats audio et vidéo ainsi que les DVD, CD audio, VCD et divers protocoles de streaming.

### 3\.1、Installer VLC

```Plain Text
sudo apt update
sudo apt install vlc -y
```

![Screenshot from 2025\-07\-30 17\-05\-31\.png](../en/images/Screenshot%20from%202025-07-30%2017-05-31.png)

### 3\.2、Utiliser VLC

Ouvrez la barre de menus des applications et cliquez sur l'icône `VLC media player`, ou saisissez la commande de démarrage dans le terminal : sélectionnez la caméra USB, la caméra CSI n'affiche aucun aperçu.

```Plain Text
vlc
```

![Screenshot from 2025\-07\-30 17\-06\-32\.png](../en/images/Screenshot%20from%202025-07-30%2017-06-32.png)

![Screenshot from 2025\-07\-30 17\-07\-09\.png](../en/images/Screenshot%20from%202025-07-30%2017-07-09.png)

Sélectionnez le numéro de périphérique correspondant à la caméra USB :

![截图\_20250925170820\.png](../en/images/截图_20250925170820.png)

![Screenshot from 2025\-07\-30 17\-08\-35\.png](../en/images/Screenshot%20from%202025-07-30%2017-08-35.png)



