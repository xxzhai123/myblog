---
layout: post
title: "Gnome Quik Query"
subtitle: "Gnome 速查"
date: 2021-09-02
author: "Seeyou"
header-img: "img/post-bg-2015.jpg"
tags: [Gnome, Quik Query]
---

# Awesome Gnome

## Preface
## Examples

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
