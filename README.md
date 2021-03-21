# 采用在线IDE，更新git/更新旧的go版本

今天学习用goormIDE在线IDE学习git，原来在上家公司学了一点，今天重拾起来：


Ubuntu下git版本升级

1、查看git版本

git --version

2、升级Git

sudo apt update  # 更新源
sudo apt install software-properties-common # 安装 PPA 需要的依赖
sudo add-apt-repository ppa:git-core/ppa    # 向 PPA 中添加 git 的软件源
sudo apt-get update
sudo apt-get install git
···

This is my GitHub Pages.
Completely by online copy & paste.
