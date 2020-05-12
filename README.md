# 1.安装ssh和crontab
sudo apt install cron

# 2.查看是否缺库和是否可以正常运行
python ucas.py status 

# 3.编辑定时任务为每月1号重启
crontab -e
# 之后在最后一行输入下面这行代码，保存（每月1号的8点30分以root用户重启电脑）
30 8 1 * * /home/zocean/anaconda3/bin/python /home/zocean/REBOOT/ucas.py login 学号 密码

# 重启crontab使功能生效
service cron restart

# 查看计划任务
crontab -l



# /home/zocean/anaconda3/bin/python是python的绝对路径，可以通过which python来替换
/home/zocean/REBOOT/ucas.py是脚本的路径
学号 和 密码需要替换为登录校园网的学号和密码