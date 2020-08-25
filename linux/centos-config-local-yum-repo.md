# Centos配置本地yum源


1. 挂载本地镜像iso
2. 配置yum仓库文件`vim /etc/yum.repos.d/local.repo`
```
[local]
name=local yum repo
base_url=file:///mnt
gpgcheck=0
enabled=1
```