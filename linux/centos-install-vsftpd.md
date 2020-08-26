# centos搭建vsftpd


## 下载
```
yum install -y vsftpd
```
## 配置
> vim /etc/vsftpd/vsftpd.conf

```
anonymous_enable=NO    #禁止匿名登陆
local_enable=YES    #允许本地用户登陆
userlist_enable=YES
userlist_deny=NO    #开启白名单模式/etc/vsftpd/user_list
```

## 启动
`systemctl enable --now vsftpd`