
# 采用在线IDE，更新git/更新旧的go版本
点击[主页](https://github.com/CHHQ1/hq/edit/gh-pages/index.html) 

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

# 设置 Go 开发环境
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



This is my GitHub Pages.
Completely by online copy & paste.
