[English](../en/03-jupyterlab-usage.md) | Deutsch | [Español](../es/03-jupyterlab-usage.md) | [Français](../fr/03-jupyterlab-usage.md) | [Italiano](../it/03-jupyterlab-usage.md) | [日本語](../ja/03-jupyterlab-usage.md) | [한국어](../ko/03-jupyterlab-usage.md) | [Português (BR)](../pt-br/03-jupyterlab-usage.md) | [Português (PT)](../pt-pt/03-jupyterlab-usage.md) | [简体中文](../zh-hans/03-jupyterlab-usage.md) | [繁體中文](../zh-hant/03-jupyterlab-usage.md)

# 03、Jupyter Lab verwenden

## 1、Jupyter Lab installieren

### 1\.1、Jupyter Lab

Installieren Sie Jupyter Lab mit dem folgenden Befehl: Wenn der Download von Jupyter Lab langsam ist, können Sie eine angegebene Quelle für die Installation verwenden.

```Plain Text
sudo apt update
sudo apt install python3-pip -y
sudo pip3 install --upgrade pip
```

```Plain Text
sudo pip3 install jupyterlab
# Tsinghua-Quelle: pip3 install jupyterlab -i https://pypi.tuna.tsinghua.edu.cn/simple
# Alibaba-Cloud-Quelle: sudo pip3 install jupyterlab -i https://mirrors.aliyun.com/pypi/simple/
```

![Screenshot from 2025\-07\-30 17\-19\-24\.png](../en/images/Screenshot%20from%202025-07-30%2017-19-24.png)

![Screenshot from 2025\-07\-30 17\-19\-40\.png](../en/images/Screenshot%20from%202025-07-30%2017-19-40.png)

![Screenshot from 2025\-07\-30 17\-27\-33\.png](../en/images/Screenshot%20from%202025-07-30%2017-27-33.png)

![Screenshot from 2025\-07\-30 17\-42\-42\.png](../en/images/Screenshot%20from%202025-07-30%2017-42-42.png)

### 1\.2、Node\.js

Installieren Sie die neueste Version von Node\.js mit dem folgenden Befehl:

```Plain Text
sudo apt install curl -y
sudo curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install nodejs -y
```

![Screenshot from 2025\-07\-30 17\-46\-22\.png](../en/images/Screenshot%20from%202025-07-30%2017-46-22.png)

Version überprüfen:

```Plain Text
node -v && npm -v
```

![Screenshot from 2025\-07\-30 17\-49\-18\.png](../en/images/Screenshot%20from%202025-07-30%2017-49-18.png)

## 2、Jupyter Lab starten

Vor dem Start von Jupyter Lab müssen Sie den Standardbrowser des Systems festlegen, andernfalls erscheinen beim Start im Terminal einige Hinweise.

### 2\.1、Standardbrowser festlegen

Öffnen Sie den Chromium-Browser des Systems und wählen Sie die Einstellung des Standardbrowsers:

![CMgcbxOfzoiCYYx3PZUcuTFgnRd\.png](../en/images/CMgcbxOfzoiCYYx3PZUcuTFgnRd.png)

![Xi2zbf66OoUGDNxKeiScrC6lnEc\.png](../en/images/Xi2zbf66OoUGDNxKeiScrC6lnEc.png)

### 2\.2、Jupyter Lab starten

```Plain Text
jupyter lab
# Start ohne Browser: jupyter lab --no-browser
# Start als Administrator: sudo jupyter lab --allow-root
```

![Screenshot from 2025\-07\-30 17\-51\-54\.png](../en/images/Screenshot%20from%202025-07-30%2017-51-54.png)

![Screenshot from 2025\-07\-30 17\-52\-13\.png](../en/images/Screenshot%20from%202025-07-30%2017-52-13.png)

### 2\.3、Zugriff vom Host-Rechner

Der Host-Rechner bezeichnet den Zugriff über das Jetson-Platinensystem; greifen Sie direkt über [http://localhost:8888/](http://localhost:8888/) zu:

`http://localhost:8888/`

![Screenshot from 2025\-07\-30 17\-52\-13\.png](../en/images/Screenshot%20from%202025-07-30%2017-52-13.png)

## 3、Jupyter Lab konfigurieren

Konfigurieren Sie für Jupyter Lab den Zugriff im lokalen Netzwerk, das Zugriffspasswort, den Autostart und weitere Vorgänge.

### 3\.1、Zugriff im lokalen Netzwerk

Konfigurieren Sie, dass Geräte im selben lokalen Netzwerk im Browser IP:8888 eingeben können, um zuzugreifen!

**Hinweis: Der Zugriff über das lokale Netzwerk eines Campusnetzwerks ist in der Regel nicht möglich; testen Sie stattdessen mit einem Laptop- oder Smartphone-Hotspot.**

Zum Beispiel ist die IP der Platine 192\.168\.0\.105; über einen Browser im selben lokalen Netzwerk können Sie 192\.168\.0\.105:8888 eingeben, um auf Jupyter Lab der Platine zuzugreifen.

#### 3\.1\.1、Konfigurationsdatei erstellen

```Plain Text
sudo jupyter lab --generate-config
```

Speicherort der automatisch erstellten Konfigurationsdatei: Writing default config to: /root/\.jupyter/jupyter\_lab\_config\.py

#### 3\.1\.2、Konfigurationsdatei bearbeiten

```Plain Text
sudo gedit /root/.jupyter/jupyter_lab_config.py
```

Zu ändernder Inhalt: Klicken Sie nach der Änderung auf Speichern und schließen Sie die Datei.

Achten Sie darauf, ob vor dem Code ein \#-Zeichen steht, damit die Konfiguration wirksam wird.

```Plain Text
# Erlaubt Anfragen von beliebigen Quellen den Zugriff auf den Jupyter Lab-Server
c.ServerApp.allow_origin = '*'
# 0.0.0.0 bedeutet, alle verfügbaren Netzwerkschnittstellen zu binden und den Zugriff von jeder Adresse zu erlauben
c.ServerApp.ip = '0.0.0.0'
# Erlaubt den Start des Jupyter Lab-Servers als root-Benutzer
c.ServerApp.allow_root = True
# Den Standardport ändern, um Konflikte zu vermeiden
c.ServerApp.port = 8888
```

![Screenshot from 2025\-07\-30 17\-54\-36\.png](../en/images/Screenshot%20from%202025-07-30%2017-54-36.png)

### 3\.2、Zugriffspasswort konfigurieren

Geben Sie im Terminal den Befehl zum Festlegen des Passworts ein; die Eingabe muss zweimal erfolgen, und das eingegebene Passwort wird nicht angezeigt\!

```Plain Text
sudo jupyter lab password
```

Speicherort der automatisch erstellten Konfigurationsdatei: \[JupyterPasswordApp\] Wrote hashed password to /root/\.jupyter/jupyter\_server\_config\.json

![Screenshot from 2025\-07\-30 17\-58\-34\.png](../en/images/Screenshot%20from%202025-07-30%2017-58-34.png)

### 3\.3、Autostart-Dienst

#### 3\.3\.1、Dienstdatei bearbeiten

```Plain Text
sudo gedit /etc/systemd/system/jupyterlab.service
```

Hinzuzufügender Inhalt: Klicken Sie nach dem Hinzufügen auf Speichern und schließen Sie die Datei.

```Plain Text
[Unit]
Description=jupyterlab
After=network.target
[Service]
Type=simple
ExecStart=/usr/local/bin/jupyter-lab
config=/root/.jupyter/jupyter_lab_config.py --no-browser
User=root
Group=root
WorkingDirectory=/home/jetson/
Restart=always
RestartSec=10
[Install]
WantedBy=multi-user.target
```

root: der Benutzername des Systems

ExecStart: der Befehl zum Starten von Jupyter lab, ändern Sie ihn in den Installationspfad von JupyterLab

config: ändern Sie ihn in den Pfad der JupyterLab-Konfigurationsdatei

WorkingDirectory: das Arbeitsverzeichnis, das beim Start von Jupyter\-lab geöffnet wird; kann frei geändert werden (empfohlen: in das Benutzerverzeichnis ändern)

`Jupyter-lab-Installationspfad anzeigen: which jupyter-lab`

`Pfad der Konfigurationsdatei: siehe den oben beim Erstellen der Konfigurationsdatei angegebenen Pfad`

![Screenshot from 2025\-07\-31 13\-02\-29\.png](../en/images/Screenshot%20from%202025-07-31%2013-02-29.png)

#### 3\.3\.2、Autostart-Dienst einrichten

##### Autostart-Dienst

```Plain Text
sudo systemctl enable jupyterlab
# Autostart deaktivieren: systemctl disable jupyterlab
```

##### **Dienst starten**

```Plain Text
sudo systemctl start jupyterlab
# Dienst stoppen: sudo systemctl stop jupyterlab
```

##### **Dienststatus anzeigen**

```Plain Text
systemctl status jupyterlab
```

![Screenshot from 2025\-07\-31 13\-08\-15\.png](../en/images/Screenshot%20from%202025-07-31%2013-08-15.png)

##### Autostart beim Booten überprüfen

Greifen Sie nach dem Neustart des Systems anhand der System-IP mit einem Gerät im selben lokalen Netzwerk über Platinen-IP:8888 zu.

> Beim ersten Zugriff müssen Sie das Passwort eingeben; das Passwort entspricht den in den vorherigen Schritten festgelegten Informationen.
> 
> Zum Zeitpunkt des Screenshots ist die IP der Platine 192\.168\.0\.105, daher können Geräte im selben lokalen Netzwerk über 192\.168\.0\.105:8888 zugreifen.
> 
> 

![Screenshot from 2025\-07\-31 13\-09\-25\.png](../en/images/Screenshot%20from%202025-07-31%2013-09-25.png)

## 4、Jupyter Lab verwenden

### 4\.1、Kernel

Es wird empfohlen, bei jeder Programmausführung oder bei Programmfehlern den Kernel neu zu starten und alle Zellenausgaben zu löschen:

![Screenshot from 2025\-07\-31 15\-01\-54\.png](../en/images/Screenshot%20from%202025-07-31%2015-01-54.png)

### 4\.2、Programm ausführen

Öffnen Sie die auszuführende Programmdatei über Jupyter Lab; führen Sie das Programm aus, indem Sie die Zellen von oben nach unten nacheinander ausführen:

#### 4\.2\.1、Wird ausgeführt

Zeigt die Zelle oben links \[\*\] an, bedeutet dies, dass sie gerade ausgeführt wird:

![截图\_20250925181034\.png](../en/images/截图_20250925181034.png)

#### 4\.2\.2、Ausführung abgeschlossen

Zeigt die Zelle oben links \[Zahl\] an, gibt dies die Reihenfolge der Ausführung an: zum Beispiel \[1\] → das Programm hat den Code dieser Zelle beim ersten Lauf ausgeführt

![截图\_20250925181054\.png](../en/images/截图_20250925181054.png)



