[English](../en/03-jupyterlab-usage.md) | [Deutsch](../de/03-jupyterlab-usage.md) | [Español](../es/03-jupyterlab-usage.md) | [Français](../fr/03-jupyterlab-usage.md) | [Italiano](../it/03-jupyterlab-usage.md) | [日本語](../ja/03-jupyterlab-usage.md) | [한국어](../ko/03-jupyterlab-usage.md) | [Português (BR)](../pt-br/03-jupyterlab-usage.md) | [Português (PT)](../pt-pt/03-jupyterlab-usage.md) | 简体中文 | [繁體中文](../zh-hant/03-jupyterlab-usage.md)

# 03、Jupyter Lab使用

## 1、Jupyter Lab安装

### 1\.1、Jupyter Lab

使用下面命令安装Jupyter Lab：若安装Jupyter Lab下载速度较慢，可以使用 指定源 进行安装

```Plain Text
sudo apt update
sudo apt install python3-pip -y
sudo pip3 install --upgrade pip
```

```Plain Text
sudo pip3 install jupyterlab
# 清华源：pip3 install jupyterlab -i https://pypi.tuna.tsinghua.edu.cn/simple
# 阿里云源：sudo pip3 install jupyterlab -i https://mirrors.aliyun.com/pypi/simple/
```

![Screenshot from 2025\-07\-30 17\-19\-24\.png](../en/images/Screenshot%20from%202025-07-30%2017-19-24.png)

![Screenshot from 2025\-07\-30 17\-19\-40\.png](../en/images/Screenshot%20from%202025-07-30%2017-19-40.png)

![Screenshot from 2025\-07\-30 17\-27\-33\.png](../en/images/Screenshot%20from%202025-07-30%2017-27-33.png)

![Screenshot from 2025\-07\-30 17\-42\-42\.png](../en/images/Screenshot%20from%202025-07-30%2017-42-42.png)

### 1\.2、Node\.js

使用下面命令安装最新的Node\.js：

```Plain Text
sudo apt install curl -y
sudo curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install nodejs -y
```

![Screenshot from 2025\-07\-30 17\-46\-22\.png](../en/images/Screenshot%20from%202025-07-30%2017-46-22.png)

验证版本：

```Plain Text
node -v && npm -v
```

![Screenshot from 2025\-07\-30 17\-49\-18\.png](../en/images/Screenshot%20from%202025-07-30%2017-49-18.png)

## 2、Jupyter Lab启动

启动Jupyter Lab前需要设置系统默认浏览器，不然启动终端会出现一些提示。

### 2\.1、设置默认浏览器

打开系统Chromium浏览器选择设置默认浏览器：

![CMgcbxOfzoiCYYx3PZUcuTFgnRd\.png](../en/images/CMgcbxOfzoiCYYx3PZUcuTFgnRd.png)

![Xi2zbf66OoUGDNxKeiScrC6lnEc\.png](../en/images/Xi2zbf66OoUGDNxKeiScrC6lnEc.png)

### 2\.2、启动Jupyter Lab

```Plain Text
jupyter lab
# 无浏览器启动 jupyter lab --no-browser
# 以管理员身份启动 sudo jupyter lab --allow-root
```

![Screenshot from 2025\-07\-30 17\-51\-54\.png](../en/images/Screenshot%20from%202025-07-30%2017-51-54.png)

![Screenshot from 2025\-07\-30 17\-52\-13\.png](../en/images/Screenshot%20from%202025-07-30%2017-52-13.png)

### 2\.3、宿主机访问

宿主机指Jetson主板系统访问，直接通过[http://localhost:8888/](http://localhost:8888/)访问：

`http://localhost:8888/`

![Screenshot from 2025\-07\-30 17\-52\-13\.png](../en/images/Screenshot%20from%202025-07-30%2017-52-13.png)

## 3、Jupyter Lab配置

对Jupyter Lab配置局域网访问、访问密码、开机自启等操作。

### 3\.1、局域网访问

设置处于同一局域网的设备可以在浏览器输入IP:8888，进行访问！

**注意：校园网的局域网一般无法访问，可以更换笔记本/手机热点测试**

例如主板IP：192\.168\.0\.105；我们可以通过同一局域网下的浏览器输入192\.168\.0\.105:8888进行主板的Jupyter Lab

#### 3\.1\.1、创建配置文件

```Plain Text
sudo jupyter lab --generate-config
```

自动生成的配置文件位置：Writing default config to: /root/\.jupyter/jupyter\_lab\_config\.py

#### 3\.1\.2、修改配置文件

```Plain Text
sudo gedit /root/.jupyter/jupyter_lab_config.py
```

修改内容：修改后点击保存并关闭文件。

注意代码前有无 \# 号，确保配置生效

```Plain Text
# 允许任何来源的请求访问Jupyter Lab服务器
c.ServerApp.allow_origin = '*'
# 0.0.0.0表示绑定所有可用的网络接口，允许从任何地址访问
c.ServerApp.ip = '0.0.0.0'
# 允许以root用户身份启动Jupyter Lab服务器
c.ServerApp.allow_root = True
# 修改默认端口，避免冲突
c.ServerApp.port = 8888
```

![Screenshot from 2025\-07\-30 17\-54\-36\.png](../en/images/Screenshot%20from%202025-07-30%2017-54-36.png)

### 3\.2、配置访问密码

终端输入设置密码的命令，需要输入两次，输入密码不会显示输入的内容\!

```Plain Text
sudo jupyter lab password
```

自动生成的配置文件位置：\[JupyterPasswordApp\] Wrote hashed password to /root/\.jupyter/jupyter\_server\_config\.json

![Screenshot from 2025\-07\-30 17\-58\-34\.png](../en/images/Screenshot%20from%202025-07-30%2017-58-34.png)

### 3\.3、开机自启服务

#### 3\.3\.1、编辑服务文件

```Plain Text
sudo gedit /etc/systemd/system/jupyterlab.service
```

添加内容：添加后点击保存并关闭文件

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

root：系统的用户名

ExecStart：启动Jupyter lab的命令，修改成JupyterLab的安装路径

config：修改成JupyterLab的配置文件路径

WorkingDirectory：启动Jupyter\-lab打开的工作目录，可自行更改（推荐修改成用户目录）

`查看Jupyter-lab安装路径：which jupyter-lab`

`配置文件路径：参考上面生成配置文件的路径`

![Screenshot from 2025\-07\-31 13\-02\-29\.png](../en/images/Screenshot%20from%202025-07-31%2013-02-29.png)

#### 3\.3\.2、设置自启服务

##### 开机自启服务

```Plain Text
sudo systemctl enable jupyterlab
# 关闭开机自启 systemctl disable jupyterlab
```

##### **启动服务**

```Plain Text
sudo systemctl start jupyterlab
# 停止服务 sudo systemctl stop jupyterlab
```

##### **查看服务状态**

```Plain Text
systemctl status jupyterlab
```

![Screenshot from 2025\-07\-31 13\-08\-15\.png](../en/images/Screenshot%20from%202025-07-31%2013-08-15.png)

##### 验证开机自启

重启系统后，根据系统IP，使用同一局域网的设备访问主板IP:8888。

> 首次访问需要输入密码，密码是前面步骤设置的信息；
> 
> 截图时主板的IP是192\.168\.0\.105，所以同一局域网下的设备可以访问192\.168\.0\.105:8888
> 
> 

![Screenshot from 2025\-07\-31 13\-09\-25\.png](../en/images/Screenshot%20from%202025-07-31%2013-09-25.png)

## 4、Jupyter Lab使用

### 4\.1、内核

建议每次运行程序或者程序异常时，重启内核和清除所有单元块输出信息：

![Screenshot from 2025\-07\-31 15\-01\-54\.png](../en/images/Screenshot%20from%202025-07-31%2015-01-54.png)

### 4\.2、运行程序

通过Jupyter Lab打开需要运行的程序文件，运行程序从上往下依次运行单元块：

#### 4\.2\.1、正在运行

单元块左上方显示\[\*\]代表正在运行：

![截图\_20250925181034\.png](../en/images/截图_20250925181034.png)

#### 4\.2\.2、运行完成

单元块左上方显示\[数字\]代表运行的顺序次数：例如\[1\] → 程序在第一次运行了该单元块代码

![截图\_20250925181054\.png](../en/images/截图_20250925181054.png)



