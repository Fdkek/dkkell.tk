Go 语言环境安装：Linux 开发环境 2 个改进
方法一：从发行版仓库安装
发行版仓库中的包一般情况下会比较老，不建议使用。

方法二：下载二进制包安装
  
从 https://golang.org/dl/，下载需要的安装包。
当前最新版本是 1.12.7，下载地址是：
  
https://dl.google.com/go/go1.12.7.linux-amd64.tar.gz
下载的压缩包解压至 /usr/local：

sudo tar -C /usr/local -xzf go1.12.7.linux-amd64.tar.gz
编辑 /etc/profile（或 ~/.profile） ，增加下面的一行内容，把 go/bin 加入到 PATH：

export PATH=$PATH:/usr/local/go/bin
编辑完成后，需要重启才能生效。如果想立即生效，则执行以下命令：

source /etc/profile
或

source ~/.profile
为你的 go 选择一个 GOPATH，比如 ~/go，
编辑 ~/.bash_profile 增加下面的行：

export GOPATH=$HOME/go
source 使其立即生效：

source ~/.bash_profile
ubuntu 安装 golang 示例
卸载旧版

# sudo apt-get remove golang-go
# sudo apt-get remove --auto-remove golang-go
# sudo apt install golang-go
# 切换到用户目录


# fetching the latest version:
sudo add-apt-repository ppa:longsleep/golang-backports
sudo apt update
sudo apt install golang-go

下载

wget https://studygolang.com/dl/golang/go1.12.5.linux-amd64.tar.gz
tar -zxvf go1.12.5.linux-amd64.tar.gz
sudo mv go /usr/local/
配置

vim .bashrc

export GOROOT=/usr/local/go              # 安装目录。
export GOPATH=$HOME/go     # 工作环境
export GOBIN=$GOPATH/bin           # 可执行文件存放
export PATH=$GOPATH:$GOBIN:$GOROOT/bin:$PATH       # 添加PATH路径
source .bashrc

测试

➜  ~ go version
go version go1.12.5 linux/amd64
Copy
方法三：源码编译安装
本文为 Wiki 文章，邀您参与纠错、纰漏和优化


  
  
