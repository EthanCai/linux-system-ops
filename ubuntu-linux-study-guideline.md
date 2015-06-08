<!-- TOC depth:6 withLinks:1 updateOnSave:1 -->
- [第一阶段](#)
	- [Shell的使用](#shell)
	- [文件、目录、用户、用户组、权限](#)
	- [vim操作](#vim)
	- [常用命令](#)
- [第二阶段](#)
	- [编写Shell脚本](#shell)
	- [进程与进程控制](#)
	- [磁盘、卷](#)
	- [网络状态的查看与基本网络管理](#)
	- [常用命令](#)
- [第三阶段](#)
<!-- /TOC -->

# 第一阶段

在第一阶段，要求掌握的内容大纲如下：

## Shell的使用
- 基础概念
    - [重定向](http://www.php100.com/html/webkaifa/Linux/2010/0430/6470.html): the various ways you can cause the shell to alter where standard input of a command comes from and where standard output goes to.
        - 理解符号 `<`, `>`, `>>`
    - [管道](http://wenku.baidu.com/view/5a7aeff4f61fb7360b4c65ba.html): The shell uses a pipe to connect standard output of one command to standard input of another command.
        - 理解符号 `|`
        - 理解filter: A filter is a command that processes an input stream of data to produce an output stream of data. 比如`sort`、`tee`。
- 推荐的Shell
    - Windows下使用[Xshell](http://www.netsarang.com/products/xsh_overview.html)（其次是SecureCRT，Putty）
    - MacOS下使用[iTerm2](https://www.iterm2.com/index.html)，和[Tmux](http://tmux.sourceforge.net/)
- 了解Linux下的语言编码、文件编码、终端编码之间的关系
    - [Linux下查看文件编码，文件或文件名编码格式转换](http://blog.sina.com.cn/s/blog_6fe0d70d0101du41.html)
    - [Linux中文乱码解决办法](http://www.mutouxiaogui.cn/blog/?p=21)
- SSH的基础概念
    - [SSH原理与运用（一）](http://www.ruanyifeng.com/blog/2011/12/ssh_remote_login.html)
    - [SSH原理与运用（二）](http://www.ruanyifeng.com/blog/2011/12/ssh_port_forwarding.html)
    - [25个必须记住的SSH命令](http://os.51cto.com/art/201011/235252.htm)
    - [mac下SSH免密码登录远程服务器](http://cssor.com/mac-ssh-auto-login-server.html)
- 在后台运行命令
    - `ls -l | lpr &`
    - Control-Z: You can suspend a foreground job (stop it from running) by pressing the suspend key, usually CONTROL-Z. The shell then stops the process and disconnects standard input from the keyboard. You can put a suspended job in the background and restart it by using the `bg` command followed by the job number. You do not need to specify the job number when there is only one stopped job.
    - `fg`: connect the key-board to a program running in the background, bring it to the fore- ground.
    - `kill`: kill process like `kill 18228`, kill background job like `kill %1`
- 通配符`?`, `*`, `[]`
    - `ls memo?`
    - `ls t*`
    - `lpr part[01235]`, `lpr part[0-35]`, `ls *[^ab]`
- 终端与本地文件的交换传输
    - `scp`: [详解linux scp命令的应用](http://os.51cto.com/art/201003/187301.htm)
    - `rz`, `sz`: [用rz、sz命令在Xshell传输文件](http://www.cnblogs.com/tao560532/p/3885792.html)
- 修改主机名、修改hosts指向
    - [linux操作系统下/etc/hosts文件配置方法](http://blog.itpub.net/21639366/viewspace-604530/)
- 按任意想要的格式显示当前时间、日期
    - [每天一个linux命令（37）：date命令](http://www.cnblogs.com/peida/archive/2012/12/13/2815687.html)

## 文件、目录、用户、用户组、权限
- Linux下的用户与组的关系、如何管理用户和组
    - [Linux用户和用户组管理](http://www.chinaunix.net/old_jh/4/438660.html)
    - [浅谈Linux用户权限管理之一（用户与组的概念）](http://ixdba.blog.51cto.com/2895551/531787/)
    - [浅谈Linux用户权限管理之二（用户管理工具）](http://ixdba.blog.51cto.com/2895551/531793)
    - [浅谈Linux用户权限管理之三（文件与权限的设定）](http://ixdba.blog.51cto.com/2895551/531799)
    - [Users and Groups](https://wiki.archlinux.org/index.php/Users_and_groups)
- 文件及目录的权限及含义，如何快速计算目录权限
    - `chmod`: change file modes or Access Control Lists
    - `chown`: change file owner or group
    - `ls -l`: display file permissions
    - `cd`: [每天一个linux命令(2)：cd命令](http://www.cnblogs.com/peida/archive/2012/10/24/2736501.html)
    - 目录访问权限一些特殊的地方
        - Execute permission is redefined for a directory: It means that you can cd into the directory and/or examine files that you have permis- sion to read from in the directory. It has nothing to do with executing a file.
    - 理解ACL
- 系统自带的特殊目录及其作用
    - Practical Guide to Ubuntu Linux 3rd, page 213, Important Standard Directories and Files
    - [Linux系统默认目录](http://blog.chinaunix.net/uid-30093414-id-4797285.html)
    - [Linux的学习--系统目录](http://www.cnblogs.com/CraryPrimitiveMan/p/4444037.html)
- 使用find、grep命令结合正则表达式快速查找指定文件
    - [每天一个linux命令（19）：find 命令概览](http://www.cnblogs.com/peida/archive/2012/11/13/2767374.html)
    - [每天一个linux命令（39）：grep 命令](http://www.cnblogs.com/peida/archive/2012/12/17/2821195.html)
- 理解硬链接（hard link）和符号链接（Symbolic link）
- 文件类型与扩展名
    - [每天一个linux命令(24)：Linux文件类型与扩展名](http://www.cnblogs.com/peida/archive/2012/11/22/2781912.html)
    - Practical Guide to Ubuntu Linux 3rd, page 501, Device Special Files

## vim操作
- 阅读[vim基本操作](./vim基本操作.md)

## 常用命令

- 常用命令
    - `man`: display system manual
    - `apropos`: search command for a keyword
    - `info`, `pinfo`: a menu-based hypetext system
    - `dpkg`, `apt`, `aptitude`: 参考[包管理系统指南](http://wiki.ubuntu.org.cn/包管理系统指南)
    - `git`: 在命令行下使用git获取、创建分支、提交、合并代码
    - `sudo`: 账号间的切换、提权至root
    - Base Utilites:
        - `ls`: list the names of files
        - `cat`: display a text files
        - `rm`: delete a files
        - `less`, `more`: display a text file one screen at a time
    - Working with files:
        - `cp`: copy file
        - `mv`: move file, change the name of file
        - `lpr`: print file
        - `grep`: search for a string
        - `head`: diplay the beginning of a file
        - `tail`: display the end of a file
        - `sort`: sort lines of text
        - `uniq`: remove duplicate lines from a file
        - `diff`: compare two files
        - `file`: determine file type
    - 更多命令
        - `echo`: display text
        - `date`: display the time and date
        - `script`: record a shell session
        - `todos`, `fromdos`: convert linux and macos files to windows format
- 压缩解压相关命令
    - `bzip2`: compress a file
    - `bunzip2`: uncompress a file
    - `bzcat`: decompresses the compressed data and displays the decompressed data
    - `bzip2recover`: supports limited data recovery from media errors
    - `gzip`: compresses a file
    - `gunzip`
    - `zcat`
    - `tar`: manipulate tape archives
    - `unrar`
    - `xz`, `unxz`, `xzcat`, `lzma`, `unlzma`, `lzcat`: Compress or decompress .xz and .lzma files
- 定位命令
    - `which`, whereis: locate a utility
    - `mlocate`: mac os没有此命令
- Obtaining user and system information
    - `who`: list users on the system
    - `finger`: list users on the system
    - `w`: list users on the system
    - `hostname`: display the system name

# 第二阶段

在第二阶段，要求掌握的内容如下：

## 编写Shell脚本

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
- 语法
    - 参考：见Practical Guide to Ubuntu Linux 3rd, Chapter 27, page 953

## 进程与进程控制

- 基础概念
    - 进程号、父子进程关系
    - 僵尸进程: [Linux僵尸进程](http://coolshell.cn/articles/656.html)
    - 孤儿进程: [孤儿进程与僵尸进程](http://www.cnblogs.com/anker/p/3271773.html)
    - [信号](http://www.cnblogs.com/taobataoma/archive/2007/08/30/875743.html)
    - 磁盘、卷
- 实践
    - `ps`: 使用PS查看进程信息，了解每一列的含义，掌握其参数
    - `top`: 使用top查看系统负载，了解每一列的含义
    - `kill`: 通过kill给进程发送信号，参考:
        - [每天一个linux命令（42）：kill命令](http://www.cnblogs.com/peida/archive/2012/12/20/2825837.html)
        - [Linux进程间通信——使用信号](http://blog.csdn.net/ljianhui/article/details/10128731)
    - `du`, `df`: 磁盘信息统计
    - 通过/proc查看系统运行信息
    - [让进程在后台可靠运行的几种方法](https://www.ibm.com/developerworks/cn/linux/l-cn-nohup/)

## 磁盘、卷

- 基础概念
    - [浅谈Linux磁盘存储管理续](http://ixdba.blog.51cto.com/2895551/562111/)

## 网络状态的查看与基本网络管理

- 概念
    - 网络协议的层次结构，参考[互联网协议入门（一）](http://www.ruanyifeng.com/blog/2012/05/internet_protocol_suite_part_i.html)
    - IP协议，IP地址的分类，子网掩码
    - TCP协议
    - UDP协议
    - PPP协议
    - Common daemons(守护进程) in linux: 见Practical Guide to Ubuntu Linux 3rd, page 402
- 网络工具
    - 修改/etc/hosts
    - OpenSSH
        - `scp` vs `rcp`
        - `ssh` vs `rsh`
    - `ifconfig`:
    - `telnet`:
    - `ftp`:
    - `ping`: use ICMP
    - `traceroute`: traces a route over the internet
    - `host`, `dig`: query internet nameservers
    - `whois`: look up information about a internet site
    - `netstat`:
    - `lsof`:

## 常用命令


# 第三阶段

在第三阶段，要求掌握的内容如下：
