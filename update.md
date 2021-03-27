# [回到主页](https://dkkell.tk/index.html) 
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
```
windows: 用户目录\AppData\Roaming\go\env 
linux:   /root/.config/go/env
```
可能是用root用户安装的，其他用户安装的可以看看 home目录下的 .config/go/env


Go version >= 1.13 当你的GO的版本大于1.13的时候
当你安装的GO的语言版本大于1.13的时候，那么就不用这么麻烦了，直接使用go env -w命令就行了
```
go env -w GOPROXY=https://goproxy.io,direct
# Set environment variable allow bypassing the proxy for selected modules
go env -w GOPRIVATE=*.corp.example.com
go env -w GO111MODULE=on
```

这个我试过，**即使你关闭了终端，新打开，还是可以的，这个命令比较的无伤害**


推荐，在/etc/profile.d/这个文件夹下面，写一个 go.sh文件，设置
```
# Enable the go modules feature
export GO111MODULE=on 

# Set the GOPROXY environment variable
export GOPROXY=https://goproxy.io  
```
当然，你也可以只给自己当前的登录用户使用，那就设置自己的profile的加载. 

那就是这俩文件：.bashrc或者.bash_profile文件
(Or, write it into the .bashrc or .bash_profile file.) 
1. 对所有用户都生效，则在/etc/profile文件中添加
2. 如果仅针对当前用户，那么你在~/.bash_profile文件中修改
3. 打开文件后，添加下面的语句

```
export GOROOT=/home/benben/go  #GOROOT是你go安装的路径
export GOBIN=$GOROOT/bin
export GOPATH=/home/benben/go_project #GOPATH是你的工作目录，可以任意指定一个地方
export PATH=$PATH:$GOPATH:$GOBIN:$GOPATH
```

编辑完成后，保存退出。根据你修改的文件，**执行source命令**，使修改立即生效。
执行go env，测试配置是否成功。

# 删除 go 版本升级
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

下载更新的版本，假设放在/home/benben/目录下。下载的压缩包为go1.12.6.linux-amd64.tar.gz。

解压tar -xzvf go1.12.6.linux-amd64.tar.gz到当前目录

接着找到你机器上的go安装位置，可以通过echo $GOROOT查看。**一般为usr/local/go**

将解压的文件夹go移动到usr/local目录下，如果移动不能覆盖内容，那么直接删除掉usr/local/go目录，再进行移动
```
$ mv /home/benben/go /usr/local/
```
移动完成后，输入命令go --version查看版本。如果为你下载的，说明更新成功。
