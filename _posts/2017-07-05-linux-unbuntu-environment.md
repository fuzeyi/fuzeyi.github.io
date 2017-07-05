---
layout: post
title:  Ubuntu环境是怎么搭建的
date:   2017-07-05 20:34:00 +0800
categories: Linux
tag: Ubuntu
---

* content
{:toc}


# 什么是软件源？ #

    软件源是debian系的概念；也就是相当于软件仓库，跟mac的app store差不多，需要什么软件，可以通过apt-get命令去搜索安装。Ubuntu的软件源一般位于/etc/apt/sources.list，我们可以根据自己的所处的位置，选择速度最快的软件源。

## 1. 怎么修改软件源呢？ ##
 
    在终端执行如下命令：
    sudo cp /etc/apt/sources.list /etc/apt/sources.list.backup 
    sudo gedit /etc/apt/sources.list


## 2. 常见的软件源有那些呢？ ##

    官方源
    deb http://archive.ubuntu.com/ubuntu/ raring main restricted universe multiverse 
    deb http://archive.ubuntu.com/ubuntu/ raring-security main restricted universe multiverse 
    deb http://archive.ubuntu.com/ubuntu/ raring-updates main restricted universe multiverse 
    deb http://archive.ubuntu.com/ubuntu/ raring-proposed main restricted universe multiverse 
    deb http://archive.ubuntu.com/ubuntu/ raring-backports main restricted universe multiverse 
    deb-src http://archive.ubuntu.com/ubuntu/ raring main restricted universe multiverse 
    deb-src http://archive.ubuntu.com/ubuntu/ raring-security main restricted universe multiverse 
    deb-src http://archive.ubuntu.com/ubuntu/ raring-updates main restricted universe multiverse 
    deb-src http://archive.ubuntu.com/ubuntu/ raring-proposed main restricted universe multiverse 
    deb-src http://archive.ubuntu.com/ubuntu/ raring-backports main restricted universe multiverse

    163源
    deb http://mirrors.163.com/ubuntu/ trusty main restricted universe multiverse 
    deb http://mirrors.163.com/ubuntu/ trusty-security main restricted universe multiverse 
    deb http://mirrors.163.com/ubuntu/ trusty-updates main restricted universe multiverse 
    deb http://mirrors.163.com/ubuntu/ trusty-proposed main restricted universe multiverse 
    deb http://mirrors.163.com/ubuntu/ trusty-backports main restricted universe multiverse 
    deb-src http://mirrors.163.com/ubuntu/ trusty main restricted universe multiverse 
    deb-src http://mirrors.163.com/ubuntu/ trusty-security main restricted universe multiverse 
    deb-src http://mirrors.163.com/ubuntu/ trusty-updates main restricted universe multiverse 
    deb-src http://mirrors.163.com/ubuntu/ trusty-proposed main restricted universe multiverse 
    deb-src http://mirrors.163.com/ubuntu/ trusty-backports main restricted universe multiverse

    阿里云源
    deb http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse 
    deb http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse 
    deb http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse 
    deb http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse 
    deb http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse 
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse 
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse 
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse 
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse 
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse


    阿里云kali源
    deb http://mirrors.aliyun.com/kali sana main non-free contrib deb http://mirrors.aliyun.com/kali-security/ sana/updates main contrib non-free deb-src http://mirrors.aliyun.com/kali-security/ sana/updates main contrib non-free

# 系统更新 #

<br>
![Thank you very much!]({{ '/styles/images/commoncmd.jpeg' | prepend: site.baseurl }})
<br>

# 一切都离不开环境变量 #
    一般来说，使用Ubuntu进行开发都离不开环境变量，因为Ubuntu系统本身严格的权限控制，造成Ubuntu有多个环境变量配置文件，
如果不了解其执行顺序，很可能造成配置的环境变量没有生效。执行顺序如下：

    1. 当你登录并且登录shell是bash时，bash首先执行/etc/profile文件中的命令(如果该文件存在)，然后它顺序寻找~/.bash_profile、~/.bash_login或~/.profile文件，并执行找到的第一个可读文件中的命令。当登录bash退出时，它将执行~/.bash_logout文件中的命令。

    2. 当启动一个交互的bash时，它将执行~/.bashrc文件中的命令(如果该文件存在并且可读)。当非交互地启动以运行一个shell脚本时,bash将查找bash_env环境变量，确定执行文件的名称。

接下来，咱们分析一下这些环境变量配置文件的作用。

<br>
![Thank you very much!]({{ '/styles/images/configfile.jpeg' | prepend: site.baseurl }})
<br>

# 设置桌面图标 #
    下面通过rubymine这款ruby开发工具来说明怎么设置桌面图标。在桌面创建一个rubymine.desktop的文件，命令如下：
    touch rubymine.desktop chmod u+x rubymine.desktop
    说明：一定要给赋予执行权限。
    编辑文件内容如下：
    [Desktop Entry] Version=1.0 Type=Application Name=RubyMine Icon=/usr/lib/RubyMine-7.1.4/bin/rubymine.png Exec="/home/xxx/bin/xxx.sh" %f Comment=Develop with pleasure! Categories=Development;IDE; Terminal=false StartupWMClass=jetbrains-rubymine

# 那些必须记住的快捷键 #
 
    Ctrl+Alt+L：锁屏。

    Ctrl+T：在 Nautilus 打开新的 Tab。

    Ctrl+Q：退出应用。

    Ctrl+Alt+F1：切换到首个虚拟终端。

    Ctrl+Alt+F2(F3)(F4)(F5)(F6)：选择不同的虚拟终端。

    Ctrl+Alt+F7：切换到当前登录会话。

    Alt+Tab：在不同的应用之间切换显示。

    Alt+F9/F10：最小化和最大化当前窗口。

    Win+E：显示所有的工作空间，可轻松进行切换。
 