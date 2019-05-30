#coding=utf-8
import smtplib
from email.mime.text import MIMEText
from email.header import Header
 
host = 'smtp.qq.com'  # 设置发件服务器地址
port = 25  # 设置发件服务器端口号。注意，这里有SSL和非SSL两种形式
 
#发送邮箱
sender = '@qq.com'
 
#接收邮箱
receiver = '@qq.com'
 
#发送邮件主题
subject = 'Python email test'
 
#发送邮箱服务器
smtpserver = 'smtp.qq.com'
 
username = '@qq.com'  #发送邮箱用户
password = ''                #邮箱密码或授权码
 
#编写 text 类型的邮件正文
#msg = MIMEText('<html><h1>比你更忙的人都在学习！</h1></html>','html','utf-8')
msg = MIMEText('比你更忙的人都在学习！111','plain','utf-8')

msg['Subject'] = Header(subject, 'utf-8')
msg['From'] = sender 
msg['To'] = receiver
 
smtp = smtplib.SMTP()
smtp.connect('smtp.qq.com',25)
smtp.login(username, password)  # 登陆邮箱
smtp.sendmail(msg['From'], msg['To'], msg.as_string())  # 发送邮件！
print("邮件发送成功!")

smtp = smtplib.SMTP()
smtp.connect('smtp.qq.com',25)
smtp.login(username, password)  # 登陆邮箱
smtp.sendmail(msg['From'], msg['To'], msg.as_string())  # 发送邮件！
print("邮件发送成功!")

