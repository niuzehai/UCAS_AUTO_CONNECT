# 查看ipv6地址
>hostname -I

***前面是ipv4地址，后面是ipv6地址***
***可以通过手机热点使用ipv6网络***

# teamviewer ssh安装及操作

### 下载teamviewer
>wget https://download.teamviewer.com/download/linux/teamviewer_amd64.deb

### 安装teamviewer
>sudo dpkg -i teamviewer_amd64.deb

### 启动teamviewer
>sudo teamviewer --daemon start

### 设置密码
>sudo teamviewer passwd YourNewPasswd

### 查看id
>teamviewer info

### 停止/启动/重启teamviewer
>sudo teamviewer --daemon stop

>sudo teamviewer --daemon start

>sudo teamviewer --daemon restart

# ucas.py 脚本使用方法

### 1.查看连接状态
>python ucas.py status

### 2.登录校园网
>python ucas.py login 学号 密码

## 3.登出校园网
>python ucas.py logout

# ucas.py 脚本自动连接校园网设置方法
### 1.安装crontab
>sudo apt install cron

### 2.查看是否可以正常运行
>python ucas.py status 

### 3.编辑定时任务为每月1号用脚本登录校园网
>crontab -e

输入下面这行代码，保存(***每月1号的8点30分运行校园网登录脚本***)
>30 8 1 * * /home/zocean/anaconda3/bin/python /home/zocean/REBOOT/ucas.py login 学号 密码

***/home/zocean/anaconda3/bin/python*** 是python的绝对路径，通过***which python***查看

***/home/zocean/REBOOT/ucas.py*** 是脚本路径

***学号 密码*** 需要替换为登录校园网的学号和密码


### 4.重启crontab使功能生效
>service cron restart


### 5.查看计划任务是否生效
>crontab -l


