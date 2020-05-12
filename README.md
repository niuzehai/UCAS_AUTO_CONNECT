### 1.安装ssh和crontab
>sudo apt install cron

### 2.查看是否可以正常运行
>python ucas.py status 

### 3.编辑定时任务为每月1号重启
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


