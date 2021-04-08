
# 重启WSL命令

WSL终端中，无法使 reboot 命令来重启，使用重启命令将会显示如下的错误信息：

System has not been booted with systemd as init system (PID 1). Can't operate. Failed to talk to init daemon.

这是因为WSL是Windows的一个子服务，终端中无法重启Windows的服务。

# 方法一：
在Windows的服务中找到LxssManager 这个服务，右键，重启服务即可，注意此时Linux终端将会关闭！

管理员身份打开PowerShell，使用命令： 对服务 LxssManager 进行重启。
```
Get-Service LxssManager | Restart-Service 
```

# 方法二：
使用 net stop 和 net start命令?
```
//以管理员权限运行cmd
net stop LxssManager	//停止
net start LxssManager	//启动
```

# 为什么不推荐用控制台的net stop 和 net start命令?

因为这个命令你需要先stop，然后在start，需要操作两次，使用PowerShell可以一步到位。
