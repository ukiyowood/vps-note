# Go程序相关命令
```
go get -u -v github.com/kataras/iris    # 安装包
go run    # 编译执行
```
## 配置安装包加速
```
go env -w GO111MODULE="on"    #开启版本管理module
go env -w GOPROXY=https://goproxy.cn,direct   #配置加速代理
```
## go mod配置
```
go init MODULE_NAME    # 初始化模块
go mod init 初始化当前文件夹, 创建go.mod文件
go mod edit 编辑go.mod文件
go mod graph 打印模块依赖图
go mod tidy 增加缺少的module，删除无用的module
go mod vendor 将依赖复制到vendor下
go mod verify 校验依赖
go mod why 解释为什么需要依赖
go mod download 下载依赖的module到本地cache（默认为$GOPATH/pkg/mod目录）
```
### 依赖替换replace
在国内访问golang.org/x的各个包都需要翻墙，你可以在go.mod中使用replace替换成github上对应的库

```
replace (
    golang.org/x/crypto v0.0.0-20180820150726-614d502a4dac => github.com/golang/crypto v0.0.0-20180820150726-614d502a4dac
    golang.org/x/net v0.0.0-20180821023952-922f4815f713 => github.com/golang/net v0.0.0-20180826012351-8a410e7b638d
    golang.org/x/text v0.3.0 => github.com/golang/text v0.3.0
)
```
