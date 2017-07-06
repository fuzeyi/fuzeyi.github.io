---
layout: post
title:  Linux快捷键和常用命令
date:   2017-07-05 22:58:00 +0800
categories: Linux
tag: Command
---

* content
{:toc}


# 快捷键 #

    Ctrl+C  //终止一条命令

    Ctrl+Z  //撤销一条命令

    Ctrl+l  //清屏

# 常用命令 #    

## 1. Ctrl+l   //清屏 ##
## 2. cd命令用来切换目录 ##
    cd 目录路径

    cd ../  切换到上级目录

    cd /    切换到根目录

## 3. man命令 退出的话直接按q ##
## 4. mkdir创建目录 ##
    mkdir 目录名

    mkdir –p 可创建级联目录

    mkdir –m xyx目录名 （xyz表示数字赋予权限）

## 5. rmdir删除空目录 ##
    rmdir 目录名

    rm –rf 目录名

## 6. 文件编辑命令（输入法英文模式） ##
    调用方法：vi a.txt（如果a.txt不存在，则创建）

    按键盘I 进入编辑模式

    退出先按esc键, 不保存退出输入 :q!；

                   保存退出输入 :wq

    输入/，进入搜索模式，输入搜索内容再按回车键

    按G: 直接定位到最末尾

    按g: 定位到首行

## 7. ls查看目录及文件 ##
    ls 路径

    ls -a  //可查看当前目录所有的文件夹

    ls -l  //可查看文件属性，可简写为ll

## 8. 复制 ##
    cp 文件名或目录 目标地址

    cp -R  //拷贝目录以及目录下的所有目录和文件

    cp a.txt b.txt  //将a.txt文件复制，且另命名为b.txt文件（目录名）
    
## 9. 移动 ##
    mv文件名或者目录名 目标地址

    mv a.txt ../         //将a文件移动到上级目录

    mv a.txt ../b.txt    //将a文件移动到上级目录并改名为b.txt

## 10. 删除 ##
    rm –rf 目录名或者文件名

## 11. 查找文件 ##
    find【选项】【路径】

    find . -name “*.log”       //在当前目录查找以.log结尾的文件

    find / -name log          //在根目录查找log命名的文件

## 12. grep命令: 在制定文件中查找字符（串）并打印该行 ##
    grep 字符串 文件名

## 13. 显示文本内容 ##
    cat 文件名

    head -n num 文件名  //head –n 2 文件名

## 14. 查看进程 ##    
    ps –ef    //显示所有运行进程，并显示启动进程的命令

## 15. 查看网络状况 ##  
    netstat -apn

    an: 按一定顺序排列输出

    p: 表示显示哪个进程在调用

## 16. 管道命令|:将前一个命令输出作为后一个命令输入 ##  
    通过命令查找进程：ps –ef | grep tomcat

    再杀掉此进程: kill -9 进程号

## 17. 权限赋予命令 ##  
    d表示目录，-表示文件

    10位表示的意义：如下图

    chmod 语法：chmod xyz 文件或者目录 chmod 777 file

    644 执行 chmod 755 text.sh 后如下图，赋予执行权限

    直接全部加上某个权限，下面代码的意思是将text.sh文件全部加上x（执行）权限

    a+w；o+w去了解用法）
## 18. 压缩解压 ## 
    将test文件夹压缩成test.tar.gz：

    tar –czvf test.tar.gz test

    将test.tar.gz解压得到test：

    tar –xzvf test.tar.gz

    将文件压缩成zip格式，使用zip命令：（必须带-r，要不然只会生成一个空文件夹）

    zip –r test.zip test

    解压：

    unzip test.zip

    -c:建立压缩档案

    -x：解压

    -t：查看内容

    -r：向压缩归档文件末尾追加文件

    -u：更新原压缩包中的文件

    这五个是独立的命令，压缩解压都要用到其中一个，可以和别的命令连用但只能用其中一个。下面的参数是根据需要在压缩或解压档案时可选的。

    -z：有gzip属性的

    -j：有bz2属性的

    -Z：有compress属性的

    -v：显示所有过程

    -O：将文件解开到标准输出

    下面的参数-f是必须的：

    -f:使用档案名字，切记，这个参数是最后一个参数，后面只能接档案名。

    总结

    1、*.tar 用 tar -xvf 解压

    2、*.gz 用 gzip -d或者gunzip 解压

    3、*.tar.gz和*.tgz 用 tar -xzf 解压

    4、*.bz2 用 bzip2 -d或者用bunzip2 解压

    5、*.tar.bz2用tar -xjf 解压

    6、*.Z 用 uncompress 解压

    7、*.tar.Z 用tar -xZf 解压

    8、*.rar 用 unrar e解压

    9、*.zip 用 unzip 解压

## 19.开启、关闭防火墙 ##

    重启后会失效：

    service iptables start

    service iptables stop

    重启后生效：永久关闭开启：

    chkconfig iptables on

    chkconfig iptables off

    查看防火墙状态：

    service iptables status 

## 20.重启、关闭、退出命令 ##

    重启：reboot （其他 shutdown –r now）

    关机：halt (其他：shutdown –h now 或者 poweroff)

    注销：logout

## 21. 实例 ##

    ls / ll / ls -l #查看目录的内容

    ll（ls -l） 查看当前目录下有哪些文件或文件夹

    ps: ls -l的别名就是ll，以- 开头的，表示文件；以d 开头的，表示目录。

    lsattr查看文件属性命令

    pwd #查看当前目录的绝对路径,显示当前所在目录

    cd #跳到指定位置

    clear #清屏

    路径： 表示文件或文件夹所在的位置

    绝对路径：以/ 开头

    相对路径：.表示当前目录；..表示当前目录的上一层

    mkdir --help #查看命令的帮助信息

    man mkdir #查看命令的详细帮助

    reboot #重启

    shutdown -h 0或者init 0 /(halt -- 不建议用)#关机

    cd切换路径#cd /etc/sysconfig

    pwd查看当前路径#pwd

    whoami查看当前用户#whoami

    uname -r查linux 内核版本号#uname –r

    clear清屏命令#clear

    tab键用来路径补全功能

    netstat -an查找linux 或者windows 下所有的端口#netstat –an

    mkdir文件夹名创建文件夹，可以同时创建多个文件夹，如：mkdir d01 d02

    mkdir -p ./first/second创建多层文件夹first 和second 都不存在情况下

    建目录

    touch文件名#touch test.txt 创建文件

    rmdir d101 #删除空目录d101

    rmdir d102 d103 #同时删除两个空目录d102,d103

    rmdir -p d104/d105/ #删除d105 目录后，若d104 是空的，则连d104 一起删除

    rm -rf文件名或文件夹名 删除文件

    cp源文件路径/源文件名 目标路径 拷贝文件#cp T01/test.txt T02

    cp -R源文件路径/源目录名 目标路径 拷贝文件夹（把文件夹的所

    有内容一起拷贝）#cp -R T01 T02

    查看文件命令：(install.log) 查看日志：分析BUG 生成的原因

    （1）more 文件名 按回车一行，空格一页。不能向上下翻行。

    （2）less 文件名 按回车一行，空格一页。可以通过上下键上下翻行。

    按q 就退出。

    （3）head -n 文件名 查看文件的前n 行， n 表示你要看的行数。

    （4）tail -n 文件名 查看文件的后n 行

    （5）cat 文件名 查看文件的所有内容

    （6）cat -n 文件名 查看文件的所有内容，并显示行数

    >导入(复制) cat A > B 把A 的内容导入到B(把原来的内容覆盖)

    >>追加导入 cat A >> B ; cat A B >>C 把A 和B 的内容导入C

    mv源文件路径/源文件名 目标文件名

    文件改名或剪切文件（文件和文件夹一样操作）

    #将./T01/tt.log 文件移动到./T02，并重命名为t.log

    [root@localhost test01]# mkdir -p T01/T02

    [root@localhost test01]# touch T01/T02/tt.log

    [root@localhost test01]# mkdir T03

    [root@localhost test01]# mv T01/T02/tt.log T03/t.log

    find路径参数参数值

    ps： 参数：-name 后面跟文件名 #表示根据文件名进行查询

    [root@localhost test01]find /root/ -name suibian.log #根据文件名进行查询

    查找home 下大小为100M 的文件

    find /home/ -size +100M

    tar参数 目标文件路径和包名 被打包的文件名称

    tar -czvf t101.tar.gz T101 #将目录和文件打到当前目录下的t101.tar.gz 压缩包中(vf 必须放后面，不然会报错)

    tar -czvf /opt/t101.tar.gz T101 #将目录和文件打到/opt/t101.tgz 压缩包中

    tar -tzvf ./t101.tar.gz #查看t101.tar.gz 压缩包中的内容

    tar -xzvf t101.tar.gz #将t101.tar.gz 压缩包中的内容释放到当前目录中

    tar -xzvf t101.tar.gz -C /opt/d102/ #将t101.tar.gz 压缩包中的内容解压到/opt/d102/目录中

    #针对windows 平台下的zip 压缩包的解压

    unzip -d d101/ f101.zip #将f101.zip 解压到d101 目录下

    ifconfig -a #查ip 信息

    ping #测试网络是否连通

    who #查看有哪些用户登录了系统

    whoami #查看当前是哪个用户登录了系统

    history #查看历史命令

    cal #查看日期

    date #查看时间

    date -s "2013-03-23 16:36" #修改系统时间

    ps #查看当前终端正在运行的进程

    ps -ef #查看系统正在运行的进程

    ps -ef | grep bash #查看系统正在运行的进程名包含bash 的进程(即查看指定用户的进程)