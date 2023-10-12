---
title: 学习安装配置和使用Oh My Zsh
author: '陈琼'
date: '2023-10-07'
slug: oh-my-zsh
categories:
  - Oh-My-Zsh
tags:
  - zsh
  - terminal
toc: true
image: 'https://cdn.jsdelivr.net/gh/gigu003/db/images/ohmyzsh.png'
---
## 什么是Zsh ?

> 在理解什么什么是Zsh之前，先理解什么是shell。Shell是连接用户和Linux内核的一种应用程序，从而让用户能更加高效、安全、低成本地使用Linux内核。而Z Shell就是其中一种Linux Shell程序，简称Zsh。

Mac OS 自带了一些Shell程序，包括：bash、csh、dash、ksh、sh、tcsh和zsh。

我们可以在Mac OS的Terminal中使用下面的命令查看Mac OS自带的shell程序

```zsh
cat /etc/shells
# List of acceptable shells for chpass(1).
# Ftpd will not allow users to connect who are not using
# one of these shells.

/bin/bash
/bin/csh
/bin/dash
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
```

我们可以看到输出结果显示的最后一个就是zsh，然后我们可以看看系统里目前安装的zsh版本是哪个版本。

```zsh
zsh --version

zsh 5.9 (x86_64-apple-darwin22.0)
```

Zsh的功能很强大，但是它的配置过于复杂。也正因为如此，才有了Oh My Zsh的诞生。

## 什么是Oh My Zsh

下面是[Oh My Zsh 官网](https://ohmyz.sh)给出的**Oh My ZSH**的解释。

> Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, themes, and a few things that make you shout...

Oh My ZSH 是基于ZSH命令行的扩张工具集，提供了丰富的扩展功能。安装Oh My Zsh的前提是安装ZSH，目前版本的Mac 系统默认自动安装了Zsh。

## 如何安装

可以通过curl和wget两种方式来安装。

*curl安装命令*

```zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

*wget安装命令*

```zsh
sh -c "$(wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```

## Oh My ZSH常用设置

Zsh的配置文件存在放在用户目录下的.zshrc文件中，如果我们想进行相关的配置的时候，只需要打开该配置文件，然后进行相应的修改即可。

### 配置主题

Oh My Zsh 有[丰富的主题配置](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)，我们可以在主题列表中选择相应的主题，并记住主题的名字。

我们在终端中打开前面提到的配置文件 .zshrc

```zsh
open ~/.zshrc
```

如果你熟悉vim编辑器的话，可以用vim打开

```zsh
vim ~/.zshrc
```

我们在该配置文件找到 ZSH_THEME 变量明，我们可以看到默认的主题名是robbyrussell，把该名字改成为我们自己想要的主题名称即可。

```zsh
# Set name of the theme to load --- if set to "random", it will
# load a random theme each time oh-my-zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
ZSH_THEME="robbyrussell"
```

### 命令别名

我们可以在.zshrc文件中配置alias，可以方便的为其他命令设置别名，可以提高命令的输入效率。

下面我们列出一些git相关的别名

```html
alias g='git'

alias ga='git add'
alias gaa='git add --all'
alias gapa='git add --patch'

alias gb='git branch'
alias gba='git branch -a'
alias gbda='git branch --merged | command grep -vE "^(\*|\s*master\s*$)" | command xargs -n 1 git branch -d'
alias gbl='git blame -b -w'
alias gbnm='git branch --no-merged'
alias gbr='git branch --remote'
alias gbs='git bisect'
alias gbsb='git bisect bad'
alias gbsg='git bisect good'
alias gbsr='git bisect reset'
alias gbss='git bisect start'

alias gco="git checkout"
alias gc="git commit -m"
alias gd='git diff'
alias gf='git fetch'
alias gs="git status"
alias gsm="git summary"
alias gl="git log"
alias gm="git merge"
alias gpl="git pull"
alias gps="git push"
alias grv='git remote -v'
alias grb='git rebase'
```

我选择了自己最常用的一些命令设置了别名。

```html
alias ga='git add'
alias gaa='git add --all'
alias gc="git commit -m"
alias gpl="git pull"
alias gps="git push"
```

### 配置插件

Oh My Zsh可以安装丰富的插件，从而实现各种各样的功能，我们在安装好插件之后，需要在.zshrc文件中进行配置，才会起作用，我们相应的插件名称放入plugins=后面的括号中，配置多个插件时，插件名称之间需用空格分开。

```
plugins=(git zsh-syntax-highlighting zsh-autosuggestions git-open autojump z)
```

## 常用方法

### 改变路径

Oh My Zsh 下，改变路径不再使用cd命令，而直接使用下面的方法即可。

| 命令    | 结果                 |
| ------- | -------------------- |
| 文件夹/ |                      |
| ..      | 回到上一级目录       |
| ...     | 回到上两级目录       |
| \\      | 回到电脑根目录       |
| ~       | 回到用户根目录       |
| \-      | 回到上一次所在的目录 |

### take命令

一个三合一命令，穿件一个文件夹，并自动进入该文件夹

| 命令            | 结果                                 |
| --------------- | ------------------------------------ |
| take <url_file> | 下载gzip文件(.gz,.bz2,.xz)，并解压缩 |
| take <git_repo> | 从网络地址（http,ssh）克隆git repo   |
| take\<folder\>  | 建并进入新文件夹                     |

- zsh_stats 命令会返回包含前20个命令及执行次数的一个列表

### TAB键自动补全

Tab键自动补全是Oh My Zsh的一大特色，当我们输入一个命令只输入一半时，按下TAB键会自动显示所有可能相关的命令。

### 通配符查询

| 命令                 | 结果                                  |
| -------------------- | ------------------------------------- |
| ls\*.txt             | 列出该目录下所有扩展名为txt的文件     |
| ls\*\*/\*.txt        | 列出该目录下(包括子目录)的所有txt文件 |
| ls\*\*/(READ)\*.\*   | 找出所有文件名以READ字符起始的文件    |
| ls\*\*/\*(READ).\*   | 找出所有文件名以READ字符结尾的的文件  |
| ls\*\*/\*(READ)\*.\* | 找出所有文件名中包含READ字符的文件    |
| ls\*\*/\*(.)         | 只搜索文件                            |
| ls\*\*/\*(/)         | 只搜索文件夹                          |

### 扩充文件名和路径

| 命令                                                                                                          | 结果                                                      |
| ------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| touch name--{1..4}.txt                                                                                        | 创建文件name-1.txt,name-2.txt,name-3.txt,name-4.txt       |
| touch name.{css, js, test.js}                                                                                 | 创建具有不同扩展名的文件，name.css，name.js，name.test.js |
| cp folder/name.js{,.bak}                                                                                      | 复制文件并添加扩展名.bak                                  |
| diff folder/{new,old}/name.js                                                                                 | 查看两个文件的不同                                        |
| mkdir -p {source,build,man,help{/pages,/yelp,/images}}                                                        | 创建完整的文件夹结构                                      |
| wget[http://site.com/folder%7B1,2%7D/pic%7B001,002%7D.jpg](http://site.com/folder%7B1,2%7D/pic%7B001,002%7D.jpg) | 下载多个文件                                              |

### 提取历史命令

- !!，两个感叹号可以提取上次执行的命令
- !2，感叹号加数字可以提取前n次执行过的命令
