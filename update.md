# 改写go环境变量
使用 go env -w命令来写环境变量：
```
go env -w GOPATH=我们自己的工作区路径
```
工作区路径 就设为 /usr/naonao/go

# 打开GoMOD，再配置代理
在这里感谢「七牛云」为我们中国区的Golang开发者提供的代理服务
```
$ go env -w GO111MODULE=on
$ go env -w GOPROXY=https://goproxy.cn,direct
```
我们现在就可以打开我们的VsCode（再次感谢七牛云，从此以后我们再也不用到Github以及Golang.org上clone到本地进行install了）

使用 go env -w命令 修改的 是 用户级别的环境变量，像GO111MODULE、GOPROXY之类的可写的环境肯定是有持久化的，

那么保存路径在哪儿呢？有一个env文件：

windows: 用户目录\AppData\Roaming\go\env 

linux:   /root/.config/go/env        

可能是用root用户安装的，其他用户安装的可以看看 home目录下的 .config/go/env

# 删除go
```
sudo rm -rf /usr/local/go     #删除go
```
将下载的包解压至 /usr/local 目录   
```
tar -C /usr/local -xzf go1.4.linux-amd64.tar.gz
```
将 /usr/local/go/bin 目录添加至PATH环境变量
```
export PATH=$PATH:/usr/local/go/bin
```
