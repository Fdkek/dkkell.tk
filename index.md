## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/CHHQ1/hq/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

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

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/CHHQ1/hq/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

# 升级go
## 先删除 
rm -rf /usr/local/go

## 再看看删除干净没？
root@goorm:/workspace/golang# go version

bash: /usr/local/go/bin/go: No such file or directory

root@goorm:/workspace/golang# /usr/local/go/bin/go version

bash: /usr/local/go/bin/go: No such file or directory

## 重新下载新的二进制
wget https://dl.google.com/go/go1.15.10.linux-amd64.tar.gz
