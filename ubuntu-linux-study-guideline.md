# Preface

面向开发的Ubuntu Linux快速学习手册，掌握基本Ubuntu Linux操作和管理


# Glossary

- **PG2UL**: 代表Pratical Guide to Ubuntu Linux, 3rd


# Install Ubuntu Linux

## 目标

- 安装Ubuntu Desktop 12.04和Ubuntu Server 12.04

## 内容

- 概念
    - Ubuntu各个release版本的区别
        - [如何查看Ubuntu的版本和Linux内核版本](http://jingyan.baidu.com/article/22fe7ced60f7473002617fae.html)  
            ![](./img/2015/06/view-ubuntu-version-and-kernel-version.png)
        - LTS release：long-term support，比如14.04的支持的有效期为5年
    - Ubuntu每个release的不同edition的区别：DVD，Desktop CD，Alternate CD，Server CD，Minimal CD
        - 参考PG2UL, page 32
    - Linux下的各种文件系统的区别
        - [Ext2、Ext3和Ext4之间的区别](http://misujun.blog.51cto.com/2595192/883949)
    - Linux目录层级结构，及常见目录
        - 参考PG2UL, page 39
    - Mount Points
        - 参考PG2UL, page 35
        - 通过`mount`命令查看分区的
        - `/etc/fstab`
    - Primary, extended and logical partitions
        - 参考PG2UL, page 34，把这三个概念讲的很清楚  
            ![](./img/2015/06/primary-extended-logical-partition.png)
    - LVM: Logical Volume Manager
        - 阅读[浅谈Linux磁盘存储管理续](http://ixdba.blog.51cto.com/2895551/562111/)
        - 阅读[LVM (简体中文) - ArchLinux Wiki](https://wiki.archlinux.org/index.php/LVM_%28%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87%29)
        - 阅读[RAID](https://wiki.archlinux.org/index.php/RAID)
        - 阅读[Software RAID and LVM](https://wiki.archlinux.org/index.php/Software_RAID_and_LVM)
- 手动安装Ubuntu Desktop 14.04
- 手动安装Ubuntu Server 14.04
- 自动化安装Ubuntu Linux
    - [Preboot Execution Environment](https://en.wiki2.org/wiki/Preboot_Execution_Environment)
    - [Cobbler Quickstart Guide](http://www.cobblerd.org/manuals/quickstart/)
    - [运维自动化之Cobbler系统安装详解](http://os.51cto.com/art/201109/288604_all.htm)


# Basic Shell Knowledge

## 目标
- 掌握Shell基本概念
- 掌握基本的Shell命令

## 内容
- 基础概念
    - [重定向](http://www.php100.com/html/webkaifa/Linux/2010/0430/6470.html): the various ways you can cause the shell to alter where standard input of a command comes from and where standard output goes to.
        - 理解符号 `<`, `>`, `>>`
    - [管道](http://wenku.baidu.com/view/5a7aeff4f61fb7360b4c65ba.html): The shell uses a pipe to connect standard output of one command to standard input of another command.
        - 理解符号 `|`
        - 理解filter: A filter is a command that processes an input stream of data to produce an output stream of data. 比如`sort`、`tee`。
    - 通配符`?`, `*`, `[]`
        - `ls memo?`
        - `ls t*`
        - `lpr part[01235]`, `lpr part[0-35]`, `ls *[^ab]`
- 推荐的Shell
    - Windows下使用[Xshell](http://www.netsarang.com/products/xsh_overview.html)（其次是SecureCRT，Putty）
    - MacOS下使用[iTerm2](https://www.iterm2.com/index.html)，和[Tmux](http://tmux.sourceforge.net/)
- 在后台运行命令
    - `ls -l | lpr &`
    - Control-Z: You can suspend a foreground job (stop it from running) by pressing the suspend key, usually CONTROL-Z. The shell then stops the process and disconnects standard input from the keyboard. You can put a suspended job in the background and restart it by using the `bg` command followed by the job number. You do not need to specify the job number when there is only one stopped job.
    - `fg`: connect the key-board to a program running in the background, bring it to the fore- ground.
    - `kill`: kill process like `kill 18228`, kill background job like `kill %1`

## Shell基本命令

- `man`: display system manual
- `apropos`: search the whatis database for stringss
- `info`, `pinfo`: a menu-based hypetext system
- `sudo`: 账号间的切换、提权至root
- Base Utilites:
    - `ls`: list the names of files
    - `cat`: display a text files
    - `rm`: delete a files
    - `less`, `more`: display a text file one screen at a time
- Working with files:
    - `cp`: copy file
    - `mv`: move file, change the name of file
    - `grep`: search for a string，参考[grep命令](http://www.cnblogs.com/peida/archive/2012/12/17/2821195.html)
    - `head`: diplay the beginning of a file
    - `tail`: display the end of a file，参考[tail命令](http://www.cnblogs.com/peida/archive/2012/11/07/2758084.html)
    - `sort`: sort lines of text，参考[sort命令](http://roclinux.cn/?p=1350)
    - `uniq`: remove duplicate lines from a file，参考[uniq命令](http://www.linuxso.com/command/uniq.html)
    - `diff`: compare two files，参考[diff命令](http://www.cnblogs.com/peida/archive/2012/12/12/2814048.html)
    - `file`: determine file type
- 定位命令
    - `which`, whereis: locate a utility
    - `mlocate`: mac os没有此命令
- 更多命令
    - `echo`: display text
        - `date`: display the time and date，参考[date命令](http://www.cnblogs.com/peida/archive/2012/12/12/2814048.html)


# Install and Manage Packages

## 目标
- 安装和管理包

## 内容
- `dpkg`, `apt`, `aptitude`
    - 参考[包管理系统指南](http://wiki.ubuntu.org.cn/包管理系统指南)
    - 参考PG2UL, page 517, chapter 13 - downloading and installing software
    - Ubuntu desktop 14.04中，并没有默认安装aptitude，需要执行`sudo apt-get install aptitude`来安装
    - apt的命令包含：
        - apt-get
        - apt-cache
        - apt-file
- `git`
    - 安装git。如果已安装，忽略。
    - 在命令行下使用git获取、创建分支、提交、合并代码
    - 阅读[Pro Git (En)](https://git-scm.com/book/en/v2)， [Pro Git中文版](http://iissnan.com/progit/)
- `wget`
    - 安装wget。如果已安装，忽略。
    - 学习使用wget
    - 在线html文档，访问[wget html document](http://www.gnu.org/software/wget/manual/wget.html)
- `vim`
    - 安装vim
    - Ubuntu Desktop 14.04 默认没有安装Vim
- 安装oh-my-zsh
    - 参考[install oh my zsh in ubuntu](http://shyuan.github.io/blog/2012/07/10/install-zsh-and-oh-my-zsh-in-ubuntu-linux/)
    - 上面这篇文章最后少介绍了两个步骤
        - 执行`sudo chsh -s /bin/zsh`
        - 重启系统，打开terminal，oh-my-zsh就生效了


# SSH

## 目标

- 远程控制linux
- Shell基本命令

## 内容

- SSH
    - [SSH原理与运用（一）](http://www.ruanyifeng.com/blog/2011/12/ssh_remote_login.html)
    - [SSH原理与运用（二）](http://www.ruanyifeng.com/blog/2011/12/ssh_port_forwarding.html)
    - [OpenSSH-Server(Ubuntu Server Document)](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
    - [25个必须记住的SSH命令](http://os.51cto.com/art/201011/235252.htm)
    - [mac下SSH免密码登录远程服务器](http://cssor.com/mac-ssh-auto-login-server.html)
- 终端与本地文件的传输
    - `scp`: [详解linux scp命令的应用](http://os.51cto.com/art/201003/187301.htm)
    - 除了scp的其它文件传输方法：sftp，sshfs, rsync，参考 [how-to-copy-files-from-one-machine-to-another-using-ssh](http://unix.stackexchange.com/questions/106480/how-to-copy-files-from-one-machine-to-another-using-ssh#)
- 了解Linux下的语言编码、文件编码、终端编码之间的关系
    - [Linux下查看文件编码，文件或文件名编码格式转换](http://blog.sina.com.cn/s/blog_6fe0d70d0101du41.html)
    - [Linux中文乱码解决办法](http://www.mutouxiaogui.cn/blog/?p=21)
    - [Linux终端中文显示乱码](http://skypegnu1.blog.51cto.com/8991766/1545449)
- 练习
    - SSH
        - 在Ubuntu Server安装openssh-server
        - 在客户端操作系统上通过SSH连接Ubuntu Server
            - Mac OS X上使用Terminal
            - Windows上使用Putty、Xshell
            - Ubuntu上安装openssh-client
    - scp
        - 通过scp向server传送文件
        - 通过scp从server获取文件

## Shell基本命令

- `script`: record a shell session
- `todos`, `fromdos`: convert linux and macos files to windows format


# Basic Vim Usage

## 目标
- 掌握Vim基本操作

## 熟悉Vim

- 阅读[vim基本操作](./vim基本操作.md)


# File, Directory, User, User Group, Authority

## 目标
- 文件、目录、用户、用户组、权限
- Shell基本命令

## 内容

- Linux下的用户与组的关系、如何管理用户和组
    - [Linux用户和用户组管理](http://www.chinaunix.net/old_jh/4/438660.html)
    - [浅谈Linux用户权限管理之一（用户与组的概念）](http://ixdba.blog.51cto.com/2895551/531787/)
    - [浅谈Linux用户权限管理之二（用户管理工具）](http://ixdba.blog.51cto.com/2895551/531793)
    - [浅谈Linux用户权限管理之三（文件与权限的设定）](http://ixdba.blog.51cto.com/2895551/531799)
    - [Users and Groups](https://wiki.archlinux.org/index.php/Users_and_groups)
    - [Linux: Show The Groups a User Is In](http://www.cyberciti.biz/faq/linux-show-groups-for-user/)
- 文件及目录的权限及含义，如何快速计算目录权限
    - `chmod`: change file modes or Access Control Lists
    - `chown`: change file owner or group
    - `ls -l`: display file permissions
    - `cd`: [每天一个linux命令(2)：cd命令](http://www.cnblogs.com/peida/archive/2012/10/24/2736501.html)
    - 目录访问权限一些特殊的地方
        - Execute permission is redefined for a directory: It means that you can cd into the directory and/or examine files that you have permission to read from in the directory. It has nothing to do with executing a file.
    - 理解ACL
- 系统自带的特殊目录及其作用
    - PG2UL, page 213
    - [Linux系统默认目录](http://blog.chinaunix.net/uid-30093414-id-4797285.html)
    - [Linux的学习--系统目录](http://www.cnblogs.com/CraryPrimitiveMan/p/4444037.html)
- 使用find、grep命令结合正则表达式快速查找指定文件
    - `find`: [每天一个linux命令（19）：find 命令概览](http://www.cnblogs.com/peida/archive/2012/11/13/2767374.html)
    - `grep`: [每天一个linux命令（39）：grep 命令](http://www.cnblogs.com/peida/archive/2012/12/17/2821195.html)
    - `ack`: a tool like grep, optimized for programmers
        - [Offical website](http://beyondgrep.com/)
        - [manual of ack](./man/man-ack.txt)
- 理解硬链接（hard link）和符号链接（Symbolic link）
- 文件类型与扩展名
    - [Linux文件类型与扩展名](http://www.cnblogs.com/peida/archive/2012/11/22/2781912.html)
    - PG2UL, page 501, Device Special Files
- Obtaining user and system information
    - `who`: list users on the system
    - `finger`: list users on the system
    - `w`: list users on the system
    - `hostname`: display the system name

# Compress and Uncompress Files

## 目标

- 熟悉文件的压缩和解压

## 内容

- 阅读PG2UL， page 174, Compressing and archiving files
- [rar tar gz zip 7z 有什么区别?](http://www.zhihu.com/question/26026741)
- bzip2压缩
    - `bzip2`: compress a file
    - `bunzip2`: uncompress a file
    - `bzcat`: decompresses the compressed data and displays the decompressed data
    - `bzip2recover`: supports limited data recovery from media errors
- gzip压缩
    - `gzip`: compresses a file
    - `gunzip`
    - `zcat`
- xz压缩
    - [XZ utils](http://tukaani.org/xz/) : XZ Utils is free general-purpose data compression software with high compression ratio. XZ Utils were written for POSIX-like systems, but also work on some not-so-POSIX systems. XZ Utils are the successor to LZMA Utils. The core of the XZ Utils compression code is based on LZMA SDK, but it has been modified quite a lot to be suitable for XZ Utils. The primary compression algorithm is currently LZMA2, which is used inside the .xz container format. With typical files, XZ Utils create 30 % smaller output than gzip and 15 % smaller output than bzip2.
    - `xz`
    - `unxz`
    - `xzcat`
- 7zip压缩
    - [7zip](http://www.7-zip.org/download.html)
    - linux、freebsd、macos下的port是p7zip，ubuntu下执行`sudo apt-get install p7zip-full`安装
    - 参考
        - [linux下的压缩解压软件7zip](http://www.linuxdiyf.com/viewarticle.php?id=193969)
        - [How to use 7zip on Linux command Line](https://www.ibm.com/developerworks/community/blogs/6e6f6d1b-95c3-46df-8a26-b7efd8ee4b57/entry/how_to_use_7zip_on_linux_command_line144?lang=en)
        - [p7zip - archlinux document](https://wiki.archlinux.org/index.php/P7zip)
- zip压缩
    - zip
    - unzip
- rar压缩
    - unrar
- `tar`: manipulate tape archives


# Process

## 目标
- 进程
- 进程控制

## 内容

- 基础概念
    - 进程号、父子进程关系
    - 僵尸进程: [Linux僵尸进程](http://coolshell.cn/articles/656.html)
    - 孤儿进程: [孤儿进程与僵尸进程](http://www.cnblogs.com/anker/p/3271773.html)
    - [信号](http://www.cnblogs.com/taobataoma/archive/2007/08/30/875743.html)
    - daemons(系统服务) in linux: 见PG2UL, page 402
        - 阅读[鸟哥的Linux私房菜-认识系统服务](http://vbird.dic.ksu.edu.tw/linux_basic/0560daemons.php)
        - 阅读[守护进程详解及创建，daemon()使用](http://www.cnblogs.com/mickole/p/3188321.html)
    - [让进程在后台可靠运行的几种方法](https://www.ibm.com/developerworks/cn/linux/l-cn-nohup/)
- 实践
    - `vmstat`: Report virtual memory statistics
    - `ps`: 使用PS查看进程信息，了解每一列的含义，掌握其参数
        - 参考 [manual of ps](./man/man-ps.txt)
        - 参考 [每天一个linux命令（41）：ps命令](http://www.cnblogs.com/peida/archive/2012/12/19/2824418.html)
    - `top`: 使用top查看系统负载，了解每一列的含义
        - 参考 [manual of top](./man/man-top.txt)
        - 参考 [每天一个linux命令（44）：top命令](http://www.cnblogs.com/peida/archive/2012/12/24/2831353.html)
    - `kill`: 通过kill给进程发送信号，参考:
        - [每天一个linux命令（42）：kill命令](http://www.cnblogs.com/peida/archive/2012/12/20/2825837.html)
        - [Linux进程间通信——使用信号](http://blog.csdn.net/ljianhui/article/details/10128731)
    - `df`: 检查linux服务器的文件系统的磁盘空间占用情况
        - 参考 [每天一个linux命令（33）：df 命令](http://www.cnblogs.com/peida/archive/2012/12/07/2806483.html)
    - `du`: 查看使用空间的，但是与df命令不同的是Linux du命令是对文件和目录磁盘使用的空间的查看
        - 参考 [每天一个linux命令（34）：du 命令](http://www.cnblogs.com/peida/archive/2012/12/10/2810755.html)
    - 通过/proc查看系统运行信息
        - [深入理解linux系统下proc文件系统内容](http://www.cnblogs.com/cute/archive/2011/04/20/2022280.html)
        - [使用 /proc 文件系统来访问 Linux 内核的内容](http://www.ibm.com/developerworks/cn/linux/l-proc.html)



# Basic Network Management

## 目标

- 查看网络状态与基本网络管理

## Basic Network Management

- 概念
    - [基础网络概念](http://vbird.dic.ksu.edu.tw/linux_server/0110network_basic.php)
    - 网络协议的层次结构
        - 参考[互联网协议入门（一）](http://www.ruanyifeng.com/blog/2012/05/internet_protocol_suite_part_i.html), [互联网协议入门（二）](http://www.ruanyifeng.com/blog/2012/06/internet_protocol_suite_part_ii.html)
        - 参考[TCP IP网络协议图](./file/TCP-IP_Network_Protocol_Diagram.pdf)
    - IP协议，IP地址的分类，子网掩码
    - TCP协议
    - UDP协议
    - PPP协议
- 网络工具
    - 使用Vim修改/etc/hosts
    - 常用文件传输方式及比较
        - [Linux 上的常用文件传输方式介绍与比较](http://www.ibm.com/developerworks/cn/linux/l-cn-filetransfer/)
        - [linux下不同服务器间数据传输(rcp,scp,rsync,ftp,sftp,lftp,wget,curl)](http://blog.csdn.net/emili/article/details/6858818)
    - [Linux常用网络指令](http://linux.vbird.org/linux_server/0140networkcommand.php)
    - [linux网络配置命令之ifconfig、ip和route](http://chrinux.blog.51cto.com/6466723/1188108)
    - [Linux and Unix ifconfig command](http://www.computerhope.com/unix/uifconfi.htm)
    - `ifconfig`:
    - `telnet`:
    - `ping`: use ICMP
    - `traceroute`: traces a route over the internet
    - `host`, `dig`: DNS lookup utility
    - `whois`: look up information about a internet site
    - `netstat`:
    - `lsof`:

# Writing Shell Scripts

## 目标

- Shell的基本概念及启动过程
- 编写Shell脚本

## Writing Shell Scripts

- 基本概念
    -  login shell vs nonlogin shell, interactive shell vs noninteractive shell
        - Login shells: `/etc/profile`, `.bash_profile`, `.bash_login`, `.profile`, `.bash_logout`
        - Interactive nonlogin shells: `/etc/bashrc`, `.bashrc`
        - Noninteractive shells: `BASH_ENV`
        - [交互式shell和非交互式shell、登录shell和非登录shell的区别](http://smilejay.com/2012/10/interactive-shell-login-shell/)
    - Builtin commands that are symbols
        - `()`: subshell
        - `$()`: command substitution
        - `(())`: arithmetic evaluation
        - `$(())`: arithmetic expansion
        - `[]`: test command
        - `[[]]`: conditional expression
    - 必读：[Use the Unofficial Bash Strict Mode (Unless You Looove Debugging)](http://redsymbol.net/articles/unofficial-bash-strict-mode/)
- 语法
    - 参考：见PG2UL, page 953

# Schedule Tasks

## 目标

- 掌握cron和anacron

## 内容

- 阅读PG2UL，page 605，Scheduling Tasks
- 阅读 [crontab 定时任务](http://linuxtools-rst.readthedocs.org/zh_CN/latest/tool/crontab.html)
- [linux定时任务的设置](http://www.taobaotest.com/blogs/1506)


# Futher Reading

## Knowledge

- [The art of command line](https://github.com/jlevy/the-art-of-command-line)

## Utilites

- [Awesome Shell](https://github.com/alebcay/awesome-shell)
- [Explain Shell](http://explainshell.com/)

# FAQ

## 如何安装中文语言支持（System Settings -> Language Support）及中文输入法（System Settings -> Text Entry）

Ubuntu上的输入法情况：http://wiki.ubuntu.org.cn/%E4%B8%AD%E6%96%87%E8%BE%93%E5%85%A5%E6%B3%95

目前比较推荐Linux上的搜狗输入法：[下载地址](http://pinyin.sogou.com/linux/?r=pinyin)

搜过拼音的安装方法：
- http://blog.csdn.net/tao_627/article/details/24119037
- http://blog.csdn.net/rflyee/article/details/9472579

## 如何升级系统，安装最新的补丁和最新版本的软件

- GUI操作
    1. System Settings -> Softwares&Updates -> Select best download server，选择最佳的软件更新服务器
    2. 然后按Alt+F2组合键调出运行命令框，然后键入update-manager -d，然后升级系统
- 终端操作
    1. 修改/etc/apt/sources.list设置更新源，参考[Linux开发环境搭建与使用——ubuntu更新设置](http://blog.csdn.net/tennysonsky/article/details/44221433)
    2. 执行下面的命令，安装最新的系统补丁：sudo apt-get update && sudo apt-get dist-upgrade

## 通过Bash修改Ubuntu Software Repository的下载地址

参考：[Repositories/CommandLine](https://help.ubuntu.com/community/Repositories/CommandLine)

This page describes how to manage software repositories from the command line. 

## 如何给Ubuntu Linux虚拟机安装VMWare Tools

http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1022525

## 给Ubuntu安装SSH服务

- https://help.ubunÂtu.com/lts/serverguide/openssh-server.html
- http://os.51cto.com/art/201109/291634.htm

## Ubuntu下的包管理命令

参考[包管理系统指南](http://wiki.ubuntu.org.cn/包管理系统指南)

## 使用命令`man wget > man-wget.txt`后，打开man-wget.txt，发现有很多重复字符，或者乱码

将man手册查询命令输出到文本文件中，要求过滤掉控制字符^H（Backspace (退格)）  

`man chmod |col –b >/home/man_chmod.txt`

col命令的使用方法见[col命名详解](http://myblog.jyc.edu.cn/?p=62)
