[English](../en/03-jupyterlab-usage.md) | [Deutsch](../de/03-jupyterlab-usage.md) | Español | [Français](../fr/03-jupyterlab-usage.md) | [Italiano](../it/03-jupyterlab-usage.md) | [日本語](../ja/03-jupyterlab-usage.md) | [한국어](../ko/03-jupyterlab-usage.md) | [Português (BR)](../pt-br/03-jupyterlab-usage.md) | [Português (PT)](../pt-pt/03-jupyterlab-usage.md) | [简体中文](../zh-hans/03-jupyterlab-usage.md) | [繁體中文](../zh-hant/03-jupyterlab-usage.md)

# 03. Uso de Jupyter Lab

## 1. Instalación de Jupyter Lab

### 1\.1. Jupyter Lab

Utilice el siguiente comando para instalar Jupyter Lab: si la velocidad de descarga de Jupyter Lab es lenta, puede utilizar una fuente especificada para la instalación

```Plain Text
sudo apt update
sudo apt install python3-pip -y
sudo pip3 install --upgrade pip
```

```Plain Text
sudo pip3 install jupyterlab
# Fuente de Tsinghua: pip3 install jupyterlab -i https://pypi.tuna.tsinghua.edu.cn/simple
# Fuente de Alibaba Cloud: sudo pip3 install jupyterlab -i https://mirrors.aliyun.com/pypi/simple/
```

![Screenshot from 2025\-07\-30 17\-19\-24\.png](../en/images/Screenshot%20from%202025-07-30%2017-19-24.png)

![Screenshot from 2025\-07\-30 17\-19\-40\.png](../en/images/Screenshot%20from%202025-07-30%2017-19-40.png)

![Screenshot from 2025\-07\-30 17\-27\-33\.png](../en/images/Screenshot%20from%202025-07-30%2017-27-33.png)

![Screenshot from 2025\-07\-30 17\-42\-42\.png](../en/images/Screenshot%20from%202025-07-30%2017-42-42.png)

### 1\.2. Node\.js

Utilice el siguiente comando para instalar la versión más reciente de Node\.js:

```Plain Text
sudo apt install curl -y
sudo curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install nodejs -y
```

![Screenshot from 2025\-07\-30 17\-46\-22\.png](../en/images/Screenshot%20from%202025-07-30%2017-46-22.png)

Verificar la versión:

```Plain Text
node -v && npm -v
```

![Screenshot from 2025\-07\-30 17\-49\-18\.png](../en/images/Screenshot%20from%202025-07-30%2017-49-18.png)

## 2. Inicio de Jupyter Lab

Antes de iniciar Jupyter Lab es necesario configurar el navegador predeterminado del sistema; de lo contrario, al iniciar el terminal aparecerán algunos avisos.

### 2\.1. Configurar el navegador predeterminado

Abra el navegador Chromium del sistema y seleccione la opción de establecerlo como navegador predeterminado:

![CMgcbxOfzoiCYYx3PZUcuTFgnRd\.png](../en/images/CMgcbxOfzoiCYYx3PZUcuTFgnRd.png)

![Xi2zbf66OoUGDNxKeiScrC6lnEc\.png](../en/images/Xi2zbf66OoUGDNxKeiScrC6lnEc.png)

### 2\.2. Iniciar Jupyter Lab

```Plain Text
jupyter lab
# Iniciar sin navegador: jupyter lab --no-browser
# Iniciar como administrador: sudo jupyter lab --allow-root
```

![Screenshot from 2025\-07\-30 17\-51\-54\.png](../en/images/Screenshot%20from%202025-07-30%2017-51-54.png)

![Screenshot from 2025\-07\-30 17\-52\-13\.png](../en/images/Screenshot%20from%202025-07-30%2017-52-13.png)

### 2\.3. Acceso desde el equipo anfitrión

El equipo anfitrión se refiere al acceso desde el sistema de la placa Jetson, directamente a través de [http://localhost:8888/](http://localhost:8888/):

`http://localhost:8888/`

![Screenshot from 2025\-07\-30 17\-52\-13\.png](../en/images/Screenshot%20from%202025-07-30%2017-52-13.png)

## 3. Configuración de Jupyter Lab

Configurar en Jupyter Lab el acceso desde la red local, la contraseña de acceso, el inicio automático al arrancar y otras operaciones.

### 3\.1. Acceso desde la red local

Configure los dispositivos que se encuentren en la misma red local para que puedan acceder introduciendo IP:8888 en el navegador!

**Nota: la red local de una red de campus normalmente no permite el acceso; puede probar cambiando a un portátil o a un punto de acceso móvil**

Por ejemplo, la IP de la placa: 192\.168\.0\.105; podemos acceder al Jupyter Lab de la placa introduciendo 192\.168\.0\.105:8888 en un navegador de la misma red local

#### 3\.1\.1. Crear el archivo de configuración

```Plain Text
sudo jupyter lab --generate-config
```

Ubicación del archivo de configuración generado automáticamente: Writing default config to: /root/\.jupyter/jupyter\_lab\_config\.py

#### 3\.1\.2. Modificar el archivo de configuración

```Plain Text
sudo gedit /root/.jupyter/jupyter_lab_config.py
```

Modifique el contenido: después de modificarlo, haga clic en guardar y cierre el archivo.

Compruebe si delante del código está o no el símbolo \#, para asegurar que la configuración surta efecto

```Plain Text
# Permitir que las solicitudes de cualquier origen accedan al servidor de Jupyter Lab
c.ServerApp.allow_origin = '*'
# 0.0.0.0 indica vincular todas las interfaces de red disponibles, permitiendo el acceso desde cualquier dirección
c.ServerApp.ip = '0.0.0.0'
# Permitir iniciar el servidor de Jupyter Lab como usuario root
c.ServerApp.allow_root = True
# Modificar el puerto predeterminado para evitar conflictos
c.ServerApp.port = 8888
```

![Screenshot from 2025\-07\-30 17\-54\-36\.png](../en/images/Screenshot%20from%202025-07-30%2017-54-36.png)

### 3\.2. Configurar la contraseña de acceso

Introduzca en el terminal el comando para establecer la contraseña; es necesario introducirla dos veces; al introducir la contraseña no se muestra el contenido \!

```Plain Text
sudo jupyter lab password
```

Ubicación del archivo de configuración generado automáticamente: \[JupyterPasswordApp\] Wrote hashed password to /root/\.jupyter/jupyter\_server\_config\.json

![Screenshot from 2025\-07\-30 17\-58\-34\.png](../en/images/Screenshot%20from%202025-07-30%2017-58-34.png)

### 3\.3. Servicio de inicio automático al arrancar

#### 3\.3\.1. Editar el archivo de servicio

```Plain Text
sudo gedit /etc/systemd/system/jupyterlab.service
```

Añada el contenido: después de añadirlo, haga clic en guardar y cierre el archivo

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

root: el nombre de usuario del sistema

ExecStart: el comando para iniciar Jupyter lab; modifíquelo a la ruta de instalación de JupyterLab

config: modifíquelo a la ruta del archivo de configuración de JupyterLab

WorkingDirectory: el directorio de trabajo que abre Jupyter\-lab al iniciarse; puede cambiarlo usted mismo (se recomienda cambiarlo al directorio del usuario)

`Ver la ruta de instalación de Jupyter-lab: which jupyter-lab`

`Ruta del archivo de configuración: consulte la ruta del archivo de configuración generado anteriormente`

![Screenshot from 2025\-07\-31 13\-02\-29\.png](../en/images/Screenshot%20from%202025-07-31%2013-02-29.png)

#### 3\.3\.2. Configurar el servicio de inicio automático

##### Servicio de inicio automático al arrancar

```Plain Text
sudo systemctl enable jupyterlab
# Desactivar el inicio automático: systemctl disable jupyterlab
```

##### **Iniciar el servicio**

```Plain Text
sudo systemctl start jupyterlab
# Detener el servicio: sudo systemctl stop jupyterlab
```

##### **Ver el estado del servicio**

```Plain Text
systemctl status jupyterlab
```

![Screenshot from 2025\-07\-31 13\-08\-15\.png](../en/images/Screenshot%20from%202025-07-31%2013-08-15.png)

##### Verificar el inicio automático al arrancar

Después de reiniciar el sistema, según la IP del sistema, utilice un dispositivo de la misma red local para acceder a la IP de la placa:8888.

> En el primer acceso es necesario introducir la contraseña; la contraseña es la información configurada en los pasos anteriores;
> 
> En el momento de la captura, la IP de la placa era 192\.168\.0\.105, por lo que los dispositivos de la misma red local pueden acceder a 192\.168\.0\.105:8888
> 
> 

![Screenshot from 2025\-07\-31 13\-09\-25\.png](../en/images/Screenshot%20from%202025-07-31%2013-09-25.png)

## 4. Uso de Jupyter Lab

### 4\.1. Kernel

Se recomienda reiniciar el kernel y borrar la información de salida de todas las celdas cada vez que se ejecute el programa o cuando el programa presente anomalías:

![Screenshot from 2025\-07\-31 15\-01\-54\.png](../en/images/Screenshot%20from%202025-07-31%2015-01-54.png)

### 4\.2. Ejecutar el programa

Abra con Jupyter Lab el archivo de programa que desea ejecutar; al ejecutarlo, las celdas se ejecutan de arriba hacia abajo en orden:

#### 4\.2\.1. En ejecución

El símbolo \[\*\] mostrado en la parte superior izquierda de la celda indica que se está ejecutando:

![截图\_20250925181034\.png](../en/images/截图_20250925181034.png)

#### 4\.2\.2. Ejecución completada

El \[número\] mostrado en la parte superior izquierda de la celda indica el número de orden de ejecución: por ejemplo, \[1\] → el programa ejecutó el código de esa celda en la primera ejecución

![截图\_20250925181054\.png](../en/images/截图_20250925181054.png)



