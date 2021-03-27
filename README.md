
# 使用goormIDE学习go，更新git和go
点击[主页](https://github.com/CHHQ1/hq/blob/gh-pages/index.md) 

[改写go环境变量](https://dkkell.tk/update.html) 

今天学习用goormIDE在线IDE学习git，原来在上家公司学了一点，今天重拾起来：

# Ubuntu下git版本升级

1. 查看git版本
```
git --version
```
2. 升级Git
```
sudo apt update  # 更新源
sudo apt install software-properties-common # 安装 PPA 需要的依赖
sudo add-apt-repository ppa:git-core/ppa    # 向 PPA 中添加 git 的软件源
sudo apt-get update
sudo apt-get install git
```

# 安装 GO 二进制安装文件
首先到go官网下载go的安装包，解压，放到指定目录（这里放到了/usr/local/下了）

```
wget https://golang.org/dl/go1.15.10.linux-amd64.tar.gz
```
## 解压
```
sudo tar -xzf go1.15.10.linux-amd64.tar.gz -C /usr/local
```
## 或者用下面命令
```
tar -C /usr/local -xzf go1.15.10.linux-amd64.tar.gz

```

# 配置 Go 开发环境
1. 创建**工作空间**
2. Go代码必须放在**工作空间**内。

它其实就是一个目录，其中包含三个**子目录**：
```
src 目录包含Go的源文件，它们被组织成 包 （每个目录都对应一个包），
pkg 目录包含 包 编译后生成的库文件，
bin 目录包含 包 编译后生成可执行程序。
```

可在合适的位置创建**工作空间**和**子目录**，实例如下：
```
mkdir -p $HOME/go-work/src
mkdir -p $HOME/go-work/pkg
mkdir -p $HOME/go-work/bin
```


3. 配置环境变量

使用 vi 编辑环境变量配置文件 $HOME/.bashrc ：
```
sudo vim $HOME/.bashrc
```
进入编辑界面后 **Shift+G** 跳转至尾行，按 o 新插入一行，输入如下：
```
export GOROOT=/usr/local/go  #设置为go安装的路径，有些安装包会自动设置默认的goroot
export GOPATH=$HOME/go-work   #默认的Golang项目的工作空间
export PATH=$GOROOT/bin:$GOPATH/bin:$PATH

# export GOBIN=$GOPATH/bin   # go install命令生成的可执行文件的路径
```
之后按 Esc 键 :wq 保存退出。使配置文件生效：
```
source $HOME/.bashrc　　#注：这里不要用sudo执行，sudo无该命令
```

4. 也可以 在/etc/profile里设置环境变量

## 建立软链接
```
sudo ln -s /usr/local/go/bin/* /usr/bin/
```
## 修改/etc/profile文件加入如下内容：
```
export PATH=$PATH:/usr/local/go/bin
```
## 执行.或者source命令，重新读取配置文件
```
source /etc/profile
```

# 查看最终效果

可运行 **go env** 查看gol环境变量：
```
go env
```
正常输出则说明配置成功，同时可对环境变量设置进行校验。

注：中国大陆需要设置代理
```
$ go env -w GO111MODULE=on
$ go env -w GOPROXY=https://goproxy.cn,direct
```


This is my GitHub Pages.
Completely by online copy & paste.
