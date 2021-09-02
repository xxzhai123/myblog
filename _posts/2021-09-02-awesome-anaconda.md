---
layout: post
title: "Awesome Anaconda"
subtitle: "Anaconda 指北"
date: 2021-09-02
author: "Seeyou"
header-img: "img/post-bg-2015.jpg"
tags: [Anaconda, 指北]
---
# anaconda

## 安装

```shell
sudo gedit ~/.bashrc
# 加入 export PATH="$HOME/anaconda3/bin:$PATH"
source ~/.bashrc
```

## [卸载](https://blog.csdn.net/qq_22474567/article/details/54984257)

- 命令 python3 看是否显示 anaconda

```sh
升级conda(升级Anaconda前需要先升级conda)：
conda update conda

升级anaconda
conda update anaconda

升级spyder：conda update spyder

更新所有包
conda update --all

conda search package
conda remove package
conda list                # 查看已安装软件
安装包
conda install package

更新包
conda update package

本地安装 conda install --use-local  boost-1.59.0-py27_0.tar.bz2
~/anaconda3/pkgs/  conda 使用*.tar.bz2
```

## 添加频道

### 官方

```sh
conda config --add channels bioconda
conda config --add channels conda-forge
conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/pkgs/main
conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/pkgs/free
```

### 查看频道

显示安装的频道

> `conda config --set show_channel_urls yes`

查看已经添加的 channels

> `conda config --get channels`

已添加的 channel 在哪里查看

> `vim ~/.condarc`

```sh
# 推荐北京外国语镜像
# ~/.condarc
channels:
  - defaults
show_channel_urls: true
channel_alias: https://mirrors.bfsu.edu.cn/anaconda
default_channels:
  - https://mirrors.bfsu.edu.cn/anaconda/pkgs/main
  - https://mirrors.bfsu.edu.cn/anaconda/pkgs/free
  - https://mirrors.bfsu.edu.cn/anaconda/pkgs/r
  - https://mirrors.bfsu.edu.cn/anaconda/pkgs/pro
  - https://mirrors.bfsu.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.bfsu.edu.cn/anaconda/cloud
  msys2: https://mirrors.bfsu.edu.cn/anaconda/cloud
  bioconda: https://mirrors.bfsu.edu.cn/anaconda/cloud
  menpo: https://mirrors.bfsu.edu.cn/anaconda/cloud
  pytorch: https://mirrors.bfsu.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.bfsu.edu.cn/anaconda/cloud
```

## conda 环境

```sh
conda env list
conda create -n mypython python=3.7
conda activate mypython
conda deactivate
conda remove -n myenv --all
conda env remove -p path_to_remove

# 重命名环境
conda create -n python2 --clone py2
conda remove -n py2 --all

# 取消自动进入环境
conda config --set auto_activate_base false
```

### conda 环境迁移

可能遇到迁移环境命名错误问题，可重命名后迁移

```sh
conda create -n newName --clone
conda activate newName
conda env export > environment.yml
# 推荐，不导出平台相关信息
conda env export --no-builds > environment.yml
# 根据 yml 或 txt 配置新环境
conda env create -f environment.yml -n reciteTask
conda env create -f=requirements.txt -n reciteTask
# 根据 yml 更新指定环境
conda env update --name myenv --file local.yml
# --prune 更新时删除不用的包
conda env update --prefix ./env --file environment.yml  --prune
```

## FAQ

### conda 清理没用的安装包

```sh
conda clean -p      //删除没有用的包
conda clean -t      //tar打包
conda clean -y --all //删除所有的安装包及cache
```

### 加入 Path

```txt
F:\Anaconda3
F:\Anaconda3\Scripts
F:\Anaconda3\Library\bin
```
