---
layout: post
title: "Gnome"
subtitle: "图形桌面环境"
date: 2021-09-02
author: "Seeyou"
header-img: "img/post-bg-2015.jpg"
abstract: "GNOME是由志愿贡献者和受雇贡献者组成的GNOME计划开发，其最大的公司贡献者为红帽公司。它是一个为开发软件框架、基于这些框架来开发客户端软件及协调软件翻译和开发无障碍软件的项目。GNOME最初是GNU网络对象模型环境（GNU Network Object Model Environment）的缩写，但是已经被废弃了。是GNU计划的一部分，并且是由志愿者开发的。"
tags: [Query, Ubuntu]
---

### 如何在 Gnome Shell 中创建自定义应用程序启动器？

```sh
cd /usr/share/applications # All users
cd ~/.local/share/applications # For you only
cat nutstore-lightapp.desktop
```

图标放在上级目录中的 `icons` 文件夹中

```sh
[Desktop Entry]
Encoding=UTF-8
Type=Application
Terminal=false
Icon=nutstore-lightapp
Exec=sh -c "exec ~/.nutstore/dist/bin/nutstore-pydaemon.py --lightappFilePath %f"
StartupWMClass=net.lightapp.app.LightAppGUI
Name=Nutstore LightApp
Name[zh_CN]=坚果云轻应用
Comment=flowchart, outline notes, markdown, mindmap
Comment[zh_CN]=流程图，大纲笔记，markdown, 思维导图
Categories=Office;FlowChart;Chart;Java;
MimeType=application/x-nol;application/x-ngm;application/x-md;text/markdown;text/x-markdown;application/x-nbmx
```

## Reference

