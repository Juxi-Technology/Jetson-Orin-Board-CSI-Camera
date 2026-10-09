[English](../en/03-jupyterlab-usage.md) | [Deutsch](../de/03-jupyterlab-usage.md) | [Español](../es/03-jupyterlab-usage.md) | [Français](../fr/03-jupyterlab-usage.md) | [Italiano](../it/03-jupyterlab-usage.md) | [日本語](../ja/03-jupyterlab-usage.md) | [한국어](../ko/03-jupyterlab-usage.md) | [Português (BR)](../pt-br/03-jupyterlab-usage.md) | Português (PT) | [简体中文](../zh-hans/03-jupyterlab-usage.md) | [繁體中文](../zh-hant/03-jupyterlab-usage.md)

# 03. Utilização do Jupyter Lab

## 1. Instalação do Jupyter Lab

### 1\.1. Jupyter Lab

Utilize o comando abaixo para instalar o Jupyter Lab: se o download do Jupyter Lab estiver lento, pode utilizar uma fonte específica para a instalação

```Plain Text
sudo apt update
sudo apt install python3-pip -y
sudo pip3 install --upgrade pip
```

```Plain Text
sudo pip3 install jupyterlab
# Fonte Tsinghua: pip3 install jupyterlab -i https://pypi.tuna.tsinghua.edu.cn/simple
# Fonte Alibaba Cloud: sudo pip3 install jupyterlab -i https://mirrors.aliyun.com/pypi/simple/
```

![Screenshot from 2025\-07\-30 17\-19\-24\.png](../en/images/Screenshot%20from%202025-07-30%2017-19-24.png)

![Screenshot from 2025\-07\-30 17\-19\-40\.png](../en/images/Screenshot%20from%202025-07-30%2017-19-40.png)

![Screenshot from 2025\-07\-30 17\-27\-33\.png](../en/images/Screenshot%20from%202025-07-30%2017-27-33.png)

![Screenshot from 2025\-07\-30 17\-42\-42\.png](../en/images/Screenshot%20from%202025-07-30%2017-42-42.png)

### 1\.2. Node\.js

Utilize o comando abaixo para instalar a versão mais recente do Node\.js:

```Plain Text
sudo apt install curl -y
sudo curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install nodejs -y
```

![Screenshot from 2025\-07\-30 17\-46\-22\.png](../en/images/Screenshot%20from%202025-07-30%2017-46-22.png)

Verificar a versão:

```Plain Text
node -v && npm -v
```

![Screenshot from 2025\-07\-30 17\-49\-18\.png](../en/images/Screenshot%20from%202025-07-30%2017-49-18.png)

## 2. Arranque do Jupyter Lab

Antes de arrancar o Jupyter Lab, é necessário definir o navegador predefinido do sistema, caso contrário, aparecerão algumas mensagens no terminal.

### 2\.1. Definir o navegador predefinido

Abra o navegador Chromium do sistema e escolha definir como navegador predefinido:

![CMgcbxOfzoiCYYx3PZUcuTFgnRd\.png](../en/images/CMgcbxOfzoiCYYx3PZUcuTFgnRd.png)

![Xi2zbf66OoUGDNxKeiScrC6lnEc\.png](../en/images/Xi2zbf66OoUGDNxKeiScrC6lnEc.png)

### 2\.2. Arrancar o Jupyter Lab

```Plain Text
jupyter lab
# Arrancar sem navegador jupyter lab --no-browser
# Arrancar como administrador sudo jupyter lab --allow-root
```

![Screenshot from 2025\-07\-30 17\-51\-54\.png](../en/images/Screenshot%20from%202025-07-30%2017-51-54.png)

![Screenshot from 2025\-07\-30 17\-52\-13\.png](../en/images/Screenshot%20from%202025-07-30%2017-52-13.png)

### 2\.3. Acesso pela máquina anfitriã

A máquina anfitriã refere-se ao acesso a partir do sistema da placa Jetson; aceda diretamente através de [http://localhost:8888/](http://localhost:8888/):

`http://localhost:8888/`

![Screenshot from 2025\-07\-30 17\-52\-13\.png](../en/images/Screenshot%20from%202025-07-30%2017-52-13.png)

## 3. Configuração do Jupyter Lab

Configure no Jupyter Lab o acesso pela rede local, a palavra-passe de acesso, o arranque automático, entre outras operações.

### 3\.1. Acesso pela rede local

Configure os dispositivos na mesma rede local para acederem introduzindo IP:8888 no navegador!

**Atenção: geralmente não é possível aceder pela rede local de uma rede de campus; pode testar trocando para o hotspot de um portátil/telemóvel**

Por exemplo, IP da placa: 192\.168\.0\.105; podemos aceder ao Jupyter Lab da placa introduzindo 192\.168\.0\.105:8888 no navegador de um dispositivo na mesma rede local

#### 3\.1\.1. Criar o ficheiro de configuração

```Plain Text
sudo jupyter lab --generate-config
```

Local do ficheiro de configuração gerado automaticamente: Writing default config to: /root/\.jupyter/jupyter\_lab\_config\.py

#### 3\.1\.2. Modificar o ficheiro de configuração

```Plain Text
sudo gedit /root/.jupyter/jupyter_lab_config.py
```

Modificar o conteúdo: após a modificação, clique em guardar e feche o ficheiro.

Atenção se há ou não o símbolo \# antes do código, para garantir que a configuração tenha efeito

```Plain Text
# Permitir que pedidos de qualquer origem acedam ao servidor Jupyter Lab
c.ServerApp.allow_origin = '*'
# 0.0.0.0 indica vincular todas as interfaces de rede disponíveis, permitindo o acesso a partir de qualquer endereço
c.ServerApp.ip = '0.0.0.0'
# Permitir arrancar o servidor Jupyter Lab como utilizador root
c.ServerApp.allow_root = True
# Modificar a porta predefinida para evitar conflitos
c.ServerApp.port = 8888
```

![Screenshot from 2025\-07\-30 17\-54\-36\.png](../en/images/Screenshot%20from%202025-07-30%2017-54-36.png)

### 3\.2. Configurar a palavra-passe de acesso

No terminal, introduza o comando para definir a palavra-passe; é necessário introduzir duas vezes, e o conteúdo introduzido não será apresentado ao introduzir a palavra-passe\!

```Plain Text
sudo jupyter lab password
```

Local do ficheiro de configuração gerado automaticamente: \[JupyterPasswordApp\] Wrote hashed password to /root/\.jupyter/jupyter\_server\_config\.json

![Screenshot from 2025\-07\-30 17\-58\-34\.png](../en/images/Screenshot%20from%202025-07-30%2017-58-34.png)

### 3\.3. Serviço de arranque automático

#### 3\.3\.1. Editar o ficheiro de serviço

```Plain Text
sudo gedit /etc/systemd/system/jupyterlab.service
```

Adicionar o conteúdo: após adicionar, clique em guardar e feche o ficheiro

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

root: o nome de utilizador do sistema

ExecStart: o comando para arrancar o Jupyter lab, altere para o caminho de instalação do JupyterLab

config: altere para o caminho do ficheiro de configuração do JupyterLab

WorkingDirectory: o diretório de trabalho aberto ao arrancar o Jupyter\-lab, pode ser alterado conforme necessário (recomenda-se alterar para o diretório do utilizador)

`Verificar o caminho de instalação do Jupyter-lab: which jupyter-lab`

`Caminho do ficheiro de configuração: consulte o caminho do ficheiro de configuração gerado acima`

![Screenshot from 2025\-07\-31 13\-02\-29\.png](../en/images/Screenshot%20from%202025-07-31%2013-02-29.png)

#### 3\.3\.2. Definir o serviço de arranque automático

##### Serviço de arranque automático

```Plain Text
sudo systemctl enable jupyterlab
# Desativar o arranque automático systemctl disable jupyterlab
```

##### **Arrancar o serviço**

```Plain Text
sudo systemctl start jupyterlab
# Parar o serviço sudo systemctl stop jupyterlab
```

##### **Verificar o estado do serviço**

```Plain Text
systemctl status jupyterlab
```

![Screenshot from 2025\-07\-31 13\-08\-15\.png](../en/images/Screenshot%20from%202025-07-31%2013-08-15.png)

##### Verificar o arranque automático

Após reiniciar o sistema, de acordo com o IP do sistema, aceda ao IP da placa:8888 utilizando um dispositivo na mesma rede local.

> No primeiro acesso, é necessário introduzir a palavra-passe; a palavra-passe é a informação definida nos passos anteriores;
> 
> No momento da captura, o IP da placa era 192\.168\.0\.105, portanto dispositivos na mesma rede local podem aceder a 192\.168\.0\.105:8888
> 
> 

![Screenshot from 2025\-07\-31 13\-09\-25\.png](../en/images/Screenshot%20from%202025-07-31%2013-09-25.png)

## 4. Utilização do Jupyter Lab

### 4\.1. Kernel

Recomenda-se reiniciar o kernel e limpar as informações de saída de todas as células sempre que executar o programa ou quando o programa apresentar anomalias:

![Screenshot from 2025\-07\-31 15\-01\-54\.png](../en/images/Screenshot%20from%202025-07-31%2015-01-54.png)

### 4\.2. Executar o programa

Abra pelo Jupyter Lab o ficheiro do programa que deseja executar; ao executar o programa, as células são executadas por ordem, de cima para baixo:

#### 4\.2\.1. Em execução

O \[\*\] exibido no canto superior esquerdo da célula indica que está em execução:

![截图\_20250925181034\.png](../en/images/截图_20250925181034.png)

#### 4\.2\.2. Execução concluída

O \[número\] exibido no canto superior esquerdo da célula representa a ordem de execução: por exemplo, \[1\] → o programa executou o código dessa célula na primeira vez

![截图\_20250925181054\.png](../en/images/截图_20250925181054.png)



