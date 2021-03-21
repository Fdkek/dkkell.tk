
# 升级 go 和 git
## 先删除
```
rm -rf /usr/local/go
```
## 再看看删除干净没？
```
root@goorm:/workspace/golang# go version
bash: /usr/local/go/bin/go: No such file or directory
root@goorm:/workspace/golang# /usr/local/go/bin/go version
bash: /usr/local/go/bin/go: No such file or directory
```
## 重新下载新的go二进制安装文件
```
wget https://dl.google.com/go/go1.15.10.linux-amd64.tar.gz
```
## 解压
```
sudo tar -xzf go1.15.10.linux-amd64.tar.gz -C /usr/local
```
### 或者用下面命令
```
tar -C /usr/local -xzf go1.15.10.linux-amd64.tar.gz
```
### 最后修改/etc/profile文件加入如下内容：
```
export PATH=$PATH:/usr/local/go/bin
```
### 执行.或者source命令，重新读取配置文件
```
source /etc/profile
```
## 经过更新go二进制安装文件后，vscode安装各种包，没有再出现莫名其妙的错误了
```
Tools environment: GOPATH=/workspace/golang
Installing 3 tools at /workspace/golang/bin in module mode.
  dlv
  staticcheck
  gopls

Installing github.com/go-delve/delve/cmd/dlv (/workspace/golang/bin/dlv) SUCCEEDED
Installing golang.org/x/tools/gopls (/workspace/golang/bin/gopls) SUCCEEDED
Installing honnef.co/go/tools/cmd/staticcheck (/workspace/golang/bin/staticcheck) SUCCEEDED

All tools successfully installed. You are ready to Go :).
```


# Markdown 链接语法

You can use the [editor on GitHub](https://github.com/CHHQ1/hq/edit/gh-pages/index.md) 

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site,

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/CHHQ1/hq/settings).

The name of this theme is saved in the Jekyll `_config.yml` configuration file.
