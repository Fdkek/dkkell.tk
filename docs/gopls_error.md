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
