# gopls：GO语言服务器

gopls 实现了VS Code 的Language Server Protocol (LSP)，发音为 go please

LSP，全称 Language Server Protocol，即语言服务器协议，这是微软创建的一个协议（目前已有 Codenvy，Red Hat 和 Sourcegraph 等公司一起支持它的发展）。

定义了在编辑器或 IDE 中与语言服务器之间使用的协议，该语言服务器提供诸如自动完成，转到定义，查找所有引用等语言功能。

语言服务器索引格式（LSIF，其发音类似于“ else if”）的目标是支持开发工具或 Web UI 中的富代码导航，而不需要源代码的本地副本。

目前该协议得到了编辑器和语言社区的广泛支持。

在 VS Code 中 Go 扩展现在默认情况下会启用 gopls 语言服务器，以提供更强大的 IDE 功能和对 Go 模块更好支持。


# 解决 gopls 报错问题

Error loading workspace: gopls requires a module at the root of your workspace.

vscode 升级 gopls 到最新版本 v0.6.4 后出现以下提示：

Error loading workspace: gopls requires a module at the root of your workspace. …

## 方法一
将 gopls 的版本回退到 v0.5.5 可以解决。
```
GO111MODULE=on go get golang.org/x/tools/gopls@v0.5.5
```
## 方法二
settings.json 中添加如下配置：
```
"gopls": {
    "experimentalWorkspaceModule": true
},
```
