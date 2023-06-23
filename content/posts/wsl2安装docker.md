---
title: "Wsl2安装docker"
date: 2023-06-23T16:02:36+08:00
---

# 安装
1. [安装链接](https://docs.docker.com/desktop/windows/wsl/)
1. 以上的安装简单讲就是下载docker desktop下载并安装
# 注意事项
1. 不要在wsl2中直接apt install，如果已经install 请先卸载，因为你会发现启动时候报错
# 常见问题
## 更改镜像位置
### 背景
1. docker镜像默认是放在C盘的，如果C盘比较小的话是有问题的
### 解决办法
- 修改gui配置，先尝试该方法，如果不生效，尝试第二种
1. ![](https://img2023.cnblogs.com/blog/3097908/202305/3097908-20230519221630722-1511599964.png)
- 创建软连接方式
1. 将`C:\Users\pang\AppData\Local\Docker`备份到`C:\Users\pang\AppData\Local\Docker_bak`，如果中间出现程序占用问题，在任务管理器杀掉docker，如果还有问题建议将wsl也关闭
1. 在cmd中创建快捷方式,（注意是cmd而不是powershell，git bash没尝试过），命令如下 `mklink /j "C:\Users\pang\AppData\Local\Docker" "你的路径"`
1. 尝试启动docker desktop，如果不行，进入下一步
1. 将备份的内容全部copy到你的路径下，比如我这里就是`C:\Users\pang\AppData\Local\Docker_bak` 到你的路径下
1. 重启docker desktop即可