---
layout: post
title: "Snap"
subtitle: "Ubuntu 软件管理工具"
date: 2021-09-08
author: "Seeyou"
header-img: "img/post-bg-2015.jpg"
abstract: "snap 是 Ubuntu 软件管理工具之一，便捷，独立，安全。"
tags: [Ubuntu, Query]
---
## 目录

你现在使用的版本的文件(与current同一个文件) `/var/snap/PACKAGE/current`

存放配置文件 `meta/snap.yaml` 你可以获取到snapcraft 配置文件 `/var/snap/PACKAGE/ID`
存放数据文件的默认文件夹 `/var/snap/PACKAGE/current`

一般服务器运行的软件在目录`/var/snap`下，在桌面端运行的软件在 `~/snap`下

## 登录

```shell
# 查看自己是否通过 Ubuntu One 登录 Snap
snap whoami
# 如果显示空则：
sudo snap NEW_LOGIN
```

## 命令

```shell
snap find PACKAGE
snap info PACKAGE
snap install PACKAGE
snap install PACKAGE --dangerous 无视危险安装本地包
# 默认 stable 通道安装，这里选择候选发行版本
snap switch-channel=candidate PACKAGE
# 升级包
snap refresh
# 操纵包
snap run --shell PACKAGE
##查看安装的应用
snap list
#卸载应用
snap remove PACKAGE
snap enable PACKAGE # 开机启动
snap disable PACKAGE
```