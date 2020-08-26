# Centos7上安装docker
 
## 1. 卸载旧版本
 
```
yum remove docker \
docker-client \
docker-client-latest \
docker-common \
docker-latest \
docker-latest-logrotate \
docker-logrotate \
docker-selinux \
docker-engine-selinux \
docker-engine
```
 
 
 
## 2. 安装依赖包
 
```
yum install -y yum-utils device-mapper-persistent-data
```
 
 
 
## 3. 安装docker-ce
 
```
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
yum install docker-ce
```
 
## 4. 启动服务
 
```
systemctl enable --now docker
```
 
## 5. 配置国内源加速
 
### 1. `vim /etc/docker/daemon.json`
 
```
 
```
 