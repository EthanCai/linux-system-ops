# Preface

面向开发的Ubuntu Linux快速学习手册，掌握基本Ubuntu Linux操作和管理

# Glossary

- **PG2UL**: 代表Pratical Guide to Ubuntu Linux, 3rd

# Install Ubuntu Linux

## 目标

- 了解Ubuntu各版本的区别
- 安装Ubuntu Desktop 12.04和Ubuntu Server 12.04
- 熟悉常见目录的用途
- 了解mount point的概念
- 熟悉primary partition、extended partition、logical partition的概念

## 内容

- Ubuntu各个release版本的区别，参考下面几篇文章：
	- [List of Ubuntu releases](https://en.wiki2.org/wiki/List_of_Ubuntu_releases)
	- [Ubuntu Release](https://wiki.ubuntu.com/Releases)
	- [Download Link of Ubuntu Releases](http://releases.ubuntu.com/)
- Ubuntu每个release的不同edition的区别(参考PG2UL, page 32)
    - **DVD**: The DVD is a live/install DVD. The DVD includes all software packages supported by Ubuntu, not just those installed by default.
    - **Desktop CD**: The Desktop CD is a live/install CD
    - **Alternate CD**: The Alternate Install CD is not a live CD; it is intended for special installations only. It presents more advanced installation options than the Desktop CD does. This CD is available for PC and 64-bit PC architectures (page 29), uses the textual installer, and installs an Ubuntu system that displays either a graphical or a textual interface.
    - **Server CD**: The Server CD is not a live CD; it is intended for installation only.
    - **Minimal CD**: Not an official edition, the Minimal CD is small (5–20 megabytes) and provides a quick installation.
- Linux下的各种文件系统的区别
    - [Ext2、Ext3和Ext4之间的区别](http://misujun.blog.51cto.com/2595192/883949)
- Linux目录层级结构，及常见目录(参考PG2UL, page 39)
```bash
rwxr-xr-x   2 root root  4096 Jul 28 11:46 bin/
drwxr-xr-x   3 root root  4096 Jul 28 10:28 boot/
drwxr-xr-x  17 root root  4240 Jul 28 11:48 dev/
drwxr-xr-x  90 root root  4096 Jul 28 18:25 etc/
drwxr-xr-x   3 root root  4096 May 10 02:02 home/
drwxr-xr-x  21 root root  4096 May 10 02:01 lib/
drwxr-xr-x   2 root root  4096 Jul  8 01:10 lib64/
drwx------   2 root root 16384 May 10 01:56 lost+found/
drwxr-xr-x   4 root root  4096 May 10 01:56 media/
drwxr-xr-x   2 root root  4096 Apr 11  2014 mnt/
drwxr-xr-x   2 root root  4096 Feb 19 03:33 opt/
dr-xr-xr-x 407 root root     0 Jul 28 11:48 proc/
drwx------   2 root root  4096 May 10 01:56 root/
drwxr-xr-x  18 root root   680 Jul 28 18:26 run/
drwxr-xr-x   2 root root 12288 Jul 28 11:46 sbin/
drwxr-xr-x   2 root root  4096 Feb 19 03:33 srv/
dr-xr-xr-x  13 root root     0 Jul 28 17:24 sys/
drwxrwxrwt   2 root root  4096 Jul 28 19:17 tmp/
drwxr-xr-x  10 root root  4096 May 10 01:56 usr/
drwxr-xr-x  12 root root  4096 May 10 02:01 var/
```
- Mount Points(参考PG2UL, page 35)
    - The directory that you mount a filesystem on is called a mount point.
    - 通过`mount`命令查看分区
    - `/etc/fstab`: The file that holds the information relating partitions to mount points
- Primary, extended and logical partitions（参考PG2UL, page 34，把这三个概念讲的很清楚）
    - 一个Disk最多有4个Primary partitions
    - 只能把4个Primary partitions中的一个划分为多个logical partitions，这个被划分的primary partition就叫extended partition
    - 示意图  
![](./img/2015/06/primary-extended-logical-partition.png)
- LVM: Logical Volume Manager
    - 阅读[浅谈Linux磁盘存储管理续](http://ixdba.blog.51cto.com/2895551/562111/)
    - 阅读[LVM (简体中文) - ArchLinux Wiki](https://wiki.archlinux.org/index.php/LVM_%28%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87%29)
    - 阅读[RAID](https://wiki.archlinux.org/index.php/RAID)
    - 阅读[Software RAID and LVM](https://wiki.archlinux.org/index.php/Software_RAID_and_LVM)

## Shell基本命令

- `df`: 检查linux服务器的文件系统的磁盘空间占用情况
    - 参考 [每天一个linux命令（33）：df 命令](http://www.cnblogs.com/peida/archive/2012/12/07/2806483.html)
- `du`: 查看使用空间的，但是与df命令不同的是Linux du命令是对文件和目录磁盘使用的空间的查看
    - 参考 [每天一个linux命令（34）：du 命令](http://www.cnblogs.com/peida/archive/2012/12/10/2810755.html)

## 练习

- 手动安装Ubuntu Desktop 14.04
- 手动安装Ubuntu Server 14.04
- 自动化安装Ubuntu Linux
	- [Preboot Execution Environment](https://en.wiki2.org/wiki/Preboot_Execution_Environment)
	- [Cobbler Quickstart Guide](http://www.cobblerd.org/manuals/quickstart/)
	- [运维自动化之Cobbler系统安装详解](http://os.51cto.com/art/201109/288604_all.htm)
- 如何查看Ubuntu的版本和Linux内核版本
	- `cat /etc/issue`
	- `sudo lsb_release -a`
	- `uname -r`
	- 执行结果见下图：  
		![](./img/2015/06/view-ubuntu-version-and-kernel-version.png)



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
            - [Linux命令之tee - 重定向输出到多个文件](http://codingstandards.iteye.com/blog/833695)
            - [linux sort 命令详解](http://www.cnblogs.com/51linux/archive/2012/05/23/2515299.html)
    - 通配符`?`, `*`, `[]`
        - `ls memo?`
        - `ls t*`
        - `lpr part[01235]`, `lpr part[0-35]`, `ls *[^ab]`
- 推荐的Shell
    - 一般Linux发行版默认的shell是bash，但这里推荐Linux推荐安装zsh + [oh-my-zsh](http://ohmyz.sh/)，理由如下：
        - zsh vs bash
            - [Zsh和Bash，究竟有何不同](https://www.soimort.org/posts/163/)
            - [Zsh shell-for-humans](http://www.slideshare.net/juandebravo/zsh-shellforhumans-27933808?related=2)
            - [Why zsh is Cooler than Your Shel](http://www.slideshare.net/brendon_jag/why-zsh-is-cooler-than-your-shell?related=1)
        - 安装oh-my-zsh
            - 先确认os中是否安装了zsh，如果没有安装，先安装zsh, `sudo apt-get install zsh`
            - 按照[http://ohmyz.sh/](http://ohmyz.sh/)的方法安装oh-my-zsh
            - 如果安装完成后，默认的shell不是zsh，按照如下操作：
                - 执行`sudo chsh -s /bin/zsh`
                - 重启系统，打开terminal，oh-my-zsh就生效了
    - Windows下安装[Xshell](http://www.netsarang.com/products/xsh_overview.html)（其次是SecureCRT，Putty）
    - MacOS下安装[oh-my-zsh](http://ohmyz.sh/), [iTerm2](https://www.iterm2.com/index.html), [Tmux](http://tmux.sourceforge.net/)
        - [TMUX Manual](http://www.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man1/tmux.1?query=tmux&sec=1)
- 在后台进程管理，
    - 参考[Linux后台进程管理](http://blog.csdn.net/fengyifei11228/article/details/5737371)
        - `ls -l | lpr &`
        - Control-Z: You can suspend a foreground job (stop it from running) by pressing the suspend key, usually CONTROL-Z. The shell then stops the process and disconnects standard input from the keyboard. You can put a suspended job in the background and restart it by using the `bg` command followed by the job number. You do not need to specify the job number when there is only one stopped job.
        - `jobs`: view background jobs
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
    - `head`: diplay the beginning of a file
    - `tail`: display the end of a file，参考[tail命令](http://www.cnblogs.com/peida/archive/2012/11/07/2758084.html)
    - `sort`: sort lines of text，参考[sort命令](http://roclinux.cn/?p=1350)
    - `uniq`: remove duplicate lines from a file，参考[uniq命令](http://www.linuxso.com/command/uniq.html)
    - `diff`: compare two files，参考[diff命令](http://www.cnblogs.com/peida/archive/2012/12/12/2814048.html)
    - `file`: determine file type
- find something
    - `find`: walk a file hierarchy, [每天一个linux命令（19）：find 命令概览](http://www.cnblogs.com/peida/archive/2012/11/13/2767374.html)
    - find filenames quickly
        - `mlocate`: ubuntu, centos下使用此命令，使用前需要执行`updatedb`命令创建`/var/lib/mlocate/mlocate.db`索引文件
        - `locate`: MacOS使用此命令，使用前需要执行`sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.locate.plist`创建`/var/db/locate.database`索引文件
    - `which`, whereis: locate a utility
    - `grep`: [每天一个linux命令（39）：grep 命令](http://www.cnblogs.com/peida/archive/2012/12/17/2821195.html)
    - `ack`: a tool like grep, optimized for programmers
        - [Offical website](http://beyondgrep.com/)
- manipulate text
    - `awk`: awk是一个强大的文本分析工具，相对于grep的查找，sed的编辑，awk在其对数据分析并生成报告时，显得尤为强大。
        - [linux awk命令详解](http://www.cnblogs.com/ggjucheng/archive/2013/01/13/2858470.html)
        - [simple awk tutorial](http://www.hcs.harvard.edu/~dholland/computers/awk.html)
    - `sed`: edit text
        - [linux中sed的用法](http://www.cnblogs.com/emanlee/archive/2013/09/07/3307642.html)
- 更多命令
    - `echo`: display text
    - `date`: display the time and date，参考[date命令](http://www.cnblogs.com/peida/archive/2012/12/12/2814048.html)


# Install and Manage Packages

## 目标

- 安装和管理包
- 掌握`dpkg`, `apt`, `aptitude`命令

## 内容

- 参考内容
    - [包管理系统指南](http://wiki.ubuntu.org.cn/包管理系统指南)
    - PG2UL, page 517, chapter 13 - downloading and installing software
- Repository: Repositories hold collections of software packages and related information, includ- ing headers that describe each package and provide information on other packages the package depends on. Ubuntu maintains repositories for each of its releases.
    - main: Ubuntu-supported open-source software
    - universe: Community-maintained open-source software
    - multiverse: Software restricted by copyright or legal issues
    - restricted: Proprietary device drivers
    - partner: Packages that are not part of Ubuntu; offered by other vendors
    - backports: Packages from later releases of Ubuntu that are not available for an earlier release
- `/etc/apt/sources.list`: specifies the repositories APT searches when you ask it to find or install a package.
    - 通过命名修改repository地址为中国访问更快的"mirrors.yun-idc.com": `sudo sed -i 's/archive.ubuntu.com/mirrors.yun-idc.com/g' /etc/apt/sources.list`
- APT local package indexes is in `/var/lib/apt/lists` directory. APT uses these files to determine whether the packages on the system, and those in its cache, are the most recent versions.
- `/var/cache/apt/archives` directory holds recently downloaded deb files (page 533)
- The aptitude utility keeps very readable logs in `/var/log/aptitude`.

## Shell命令

- `dpkg`
    - 全称：Debian package management system
    - dpkg主要是对本地的软件包进行管理，本地软件包包括已经在本地安装的软件包和已经下载但还没有安装的 deb 文件，不解决依赖关系。
- `apt`
    - 全称：Advanced Package Tool
    - apt和dpkg的用途比较：APT downloads software packages, while dpkg installs, removes, maintains, manages dependencies of, and reports on software packages.
    - apt的命令包含
        - `apt-get`: 主要负责软件包的在线安装与升级，低层对 deb 包的处理还是用的 dpkg，解决依赖关系
        - `apt-cache`: 主要用来查询软件包的状态和依赖关系
        - `apt-file`: 主要负责查询软件包名称和软件包包含的文件（值得注意的是它要自己同步）
- `aptitude`
    - Ubuntu desktop 14.04中，并没有默认安装aptitude，需要执行`sudo apt-get install aptitude`来安装
    - `aptitude install`: install package and its dependencies
    - `aptitude remove`: remove package and its dependencies, but not include configuration
    - `aptitude purge`: remove package and its dependencies, configuration
    - `aptitude search`: looks for packages with names that match a pattern
    - `aptitude clean`: Deletes all packages from the APT cache
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

## 练习

### 查找软件包

`aptitude search`命令的查找结果一般如下：

```bash
➜  ~  aptitude search '~ivim'
i   vim                                                                 - Vi IMproved - enhanced vi editor                                              
i   vim-common                                                          - Vi IMproved - Common files                                                    
i A vim-runtime                                                         - Vi IMproved - Runtime files                                                   
i   vim-tiny                                                            - Vi IMproved - enhanced vi editor - compact version     
```

The letter in the first column of each entry indicates the status of the package on the system: 
- `i` for installed
- `c` for removed except for configuration files
- `p` for purged (package and configuration files removed)
- `v` for a **virtual package** (When you install certain packages, aptitude queries you and, if you agree, installs more than one package. You are either installing a package with dependencies or a virtual package, also called a metapackage. A **virtual package** is not a software package, but rather a metapackage that depends on other packages. Virtual pack- ages facilitate the installation of software that requires multiple packages.)

A second letter in the first column indicates a stored action that will be performed on the package. 
An `A` appearing as the third letter means the package was automatically installed.


```bash
dpkg --get-selections pattern #查找软件包名称包含 pattern 的软件包，可以在后面用 grep install/deinstall 来选择是否已经被 remove 的包(曾经安装过了的)
apt-cache search pattern #查找软件包名称和描述包含 pattern 的软件包 (可以是安装了也可以是没有安装)，可以用参数来限制是否已经安装
aptitude search '~ipattern' #查找已经安装的软件包
aptitude search '~cpattern' #查找已经被 remove 的软件包，还有配置文件存在
aptitude search '~npattern' #查找软件包名称包含 pattern 的软件包 (可以是安装了也可以是没有安装)
aptitude search '!~i~npattern' #查找还没有安装的软件包名字包含 pattern 的软件包。(前面的 ! 是取反的意思，反划线是 escape 符号)
注：还有很多用法，可以去看看我在 forum 中写的帖子 [aptitude Search Patterns](http://forum.ubuntu.org.cn/viewtopic.php?f=52&t=259550)

apt-cache depends package #查找名称是 package 软件包的依赖关系
aptitude search '~R~npackage' #查找名称是 package 软件包的依赖关系，可以同时看到是不是已经安装

apt-cache rdepends package #查找哪些软件包依赖于名称是 package 软件包
aptitude search '~D~npackage' #查找哪些软件包依赖于名称是 package 软件包

dpkg -I package_name.deb #参数是大写i，查找已经下载但末安装的 package_name.deb 软件包的信息
dpkg -l package #参数是小写L，查找已经安装软件包 package 的信息，精简
apt-cache show pattern ##查找软件包pattern的信息 (可以是安装了也可以是没有安装)
aptitude show ~npattern #显示名称是 pattern 软件包的信息(可以是安装了也可以是没有安装)

apt-cache policy pattern #显示 pattern 软件包的策略(可以是安装了也可以是没有安装)
apt-cache showpkg pattern #显示pattern 软件包的其它信息(可以是安装了也可以是没有安装)

dpkg -S pattern #查找已经安装的文件 pattern 属于哪个软件包
apt-file search pattern #查找文件 pattern 属于哪个软件包(可以是安装了也可以是没有安装)

dpkg -c package_name.deb #查找已经下载但末安装的 package.deb 软件包包含哪些文件
dpkg -L package #查找已经安装 package 软件包包含哪些文件
apt-file show pattern #查找 pattern 软件包(可以是安装了也可以是没有安装)包含哪些文件
```

### 下载软件包

```bash
apt-get install package -d #下载软件包
aptitude download pattern #同上，不同的是下载的是符合 pattern 的软件包，后面不再指出
```

### 安装软件包

```bash
dpkg -i package_name.deb #安装本地软件包，不解决依赖关系
apt-get install package #在线安装软件包
aptitude install pattern #同上

apt-get install package --reinstall #重新安装软件包
apitude reinstall package #同上
```

### 移除软件包

```bash
dpkg -r package #删除软件包
apt-get remove package #同上
aptitude remove package #同上

dpkg -P #删除软件包及配置文件
apt-get remove package --purge #删除软件包及配置文件
apitude purge pattern #同上
```

### 自动移除软件包

```bash
apt-get autoremove #删除不再需要的软件包
注：aptitude 没有，它会自动解决这件事
```

### 清除下载的软件包

```bash
apt-get clean #清除 /var/cache/apt/archives 目录
aptitude clean #同上

apt-get autoclean #清除 /var/cache/apt/archives 目录，不过只清理过时的包
aptitude autoclean #同上
```

### 更新源

```bash
apt-get update #更新源
aptitude update #同上
```

### 更新系统

```bash
apt-get upgrade #更新已经安装的软件包
aptitude safe-upgrade #同上
apt-get dist-upgrade #升级系统
aptitude full-upgrade #同上
```


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
- 实践
    - SSH
        - 在Ubuntu Server安装openssh-server
        - 在客户端操作系统上通过SSH连接Ubuntu Server
            - Mac OS X上使用Terminal
            - Windows上使用Putty、Xshell
            - Ubuntu上安装openssh-client
    - scp
        - 通过scp向server传送文件
        - 通过scp从server获取文件
    - [让进程在断开SSH连接后依然保持运行](https://www.ibm.com/developerworks/cn/linux/l-cn-nohup/)

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

阅读PG2UL， page 174, Compressing and archiving files

[rar tar gz zip 7z 有什么区别?](http://www.zhihu.com/question/26026741)：

    tar是Linux常见的一种归档文件（原生不包括压缩功能）
    gzip是gnu/Linux的一种压缩文件工具，算法是基于 DEFLATE，文件是gz，可以和tar组合。
    zip是一种规范开放的压缩文件，算法不定，但主要是用 DEFLATE
    rar的算法专有，但发行时附送解码器允许解码器再开发，编码器专有
    7zip和zip差不多，算法不定，主要用bzip2和lzma，而且完全开源。
    zip和7z更像是压缩容器，因为算法不是格式固定，允许支持其他压缩算法
    The zip and unzip utilities are compatible with PKZIP, a Windows program that compresses and archives files.

    大小与区别
    tar是无压缩的，比压缩效率，gz的算法最原始，所以较低，其次zip，接着rar，7z两个主要算法基本上略优于rar，基本不相上下。

    优缺点
    在Linux里面，tar一般和其他没有文件管理的压缩算法文件结合使用，用tar打包整个文件目录结构成一个文件，再用gz，bzip等压缩算法压缩成一次。也是Linux常见的压缩归档的处理方法。

    zip相对比较老，格式规范可知，所以积累了各种加解压实现，有较好的兼容性，不过现有文件格式相对而言比较落后，还有会有文件名乱码问题（因为文件名是用非Unicode编码）

    rar和7z就新些，所用算法压缩效率也好很多，兼容性不及zip，不过rar的编码器有专利，但可以不制作编码器的情况使用或者再开发发行版的解码器（所以其他压缩管理工具可以调用rar的解码器来解压rar，但不能加压，百度云的在线解压rar可能是使用或者再开发过unrar文件），7z的文件和管理程序都是开源的，文件格式也比较好（支持Unicode文件名），两个主要压缩算法的性能都很好，只是差何时能普及而取代zip而已。

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
    - zip: 参考[Linux zip command](http://linux.about.com/od/commands/l/blcmdl1_zip.htm)
    - unzip: 参考[Linux unzip command](http://linux.about.com/od/commands/l/blcmdl1_unzip.htm)
- rar压缩
    - unrar: 参考[How To Extract RAR Files Under Linux](http://www.lifelinux.com/how-to-extract-rar-files-under-linux/)
- `tar`: manipulate tape archives

## 练习

### `bzip2`, `bunzip2`, `bzcat`命令练习

```bash
#使用bzip2压缩文件默认会自动删除原文件，生成的压缩文件名是"[原文件名（包括扩展名）].bz2"
$ bzip2 -v letter_e
letter_e: 11680.00:1, 0.001 bits/byte, 99.99% saved, 584000 in, 50 out.

$ ls -l
-rw-rw-r-- 1 sam sam 50 2010-03-01 22:31 letter_e.bz2

# 使用bunzip2解压文件会自动删除原压缩文件，原文件名去掉末尾的".bz2"就是生成的解压缩文件名
$ bunzip -v letter_e.bz2

$ bzcat letter_e.bz2 | head -2
eeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee
eeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee
```

### `tar`命令练习

```bash
# === Combine files into one file ===

$ ls -l g b d
-rw-r--r-- 1 zach other 1178 2010-08-20 14:16 b
-rw-r--r-- 1 zach zach  3783 2010-08-20 14:17 d
-rw-r--r-- 1 zach zach  1302 2010-08-20 14:16 g

#  –c (create), –v (verbose), and –f (write to or read from a file)
$ tar -cvf all.tar g b d
g
b
d

$ ls -l all.tar
-rw-r--r-- 1 zach zach  9728 2010-08-20 14:17 all.tar

# –t option to display a table of contents for the archive
$ tar -tvf all.tar
-rw-r--r-- zach /zach    1302 2010-08-20 14:16 g
-rw-r--r-- zach /other   1178 2010-08-20 14:16 b
-rw-r--r-- zach /zach    3783 2010-08-20 14:17 d


# === Extract files from combined file ===

$ ls -l mak*
-rw-r--r-- 1 sam sam 1564560 2010-04-12 15:51 make-3.81.tar.gz

$ gunzip mak*
$ ls -l mak*
-rw-r--r-- 1 sam sam 6072320 2010-04-12 15:51 make-3.81.tar

# –x to extract files from a tar archive
$ tar -xvf mak*
make-3.81/
make-3.81/config/
make-3.81/config/dospaths.m4
...
make-3.81/tests/run_make_tests.pl
make-3.81/tests/test_driver.pl

# ===combine the gunzip and tar commands===

# The –c option causes gunzip to send its output through the pipe instead of creating a file. The final hyphen (–) causes tar to read from standard input.
$ gunzip -c make-3.81.tar.gz | tar -xvf -

# –z option to cause tar to call gunzip
$ tar -xvzf make-3.81.tar.gz

# -j option to cause tar to call bzip2
$ tar -xvjf make-3.81.tar.bz2
```

# Process

## 目标

- 进程
- 进程控制
- 守护进程（daemon）和服务（service）

## 内容

- 基础概念
    - 进程
        - 进程号、父子进程关系
        - 僵尸进程: [Linux僵尸进程](http://coolshell.cn/articles/656.html)
        - 孤儿进程: [孤儿进程与僵尸进程](http://www.cnblogs.com/anker/p/3271773.html)
        - [信号](http://www.cnblogs.com/taobataoma/archive/2007/08/30/875743.html)
    - 守护进程和服务
        - 概念上的区别：系统为了某些功能必须要提供一些服务 (不论是系统本身还是网络方面)，这个服务就称为 service。但是service的提供总是需要程序的运行吧！达成这个service的程序我们就称呼他为daemon！举例来说，达成循环型例行性工作排程服务 (service) 的程序为 crond 这个 daemon ！
        - daemon主要分为：
            - stand_alone，可以自行单独启动服务
            - super daemon，由一个特殊的 daemon 来统一管理
        - 参考
            - 阅读[鸟哥的Linux私房菜-认识系统服务](http://vbird.dic.ksu.edu.tw/linux_basic/0560daemons.php)
- 实践
    - 通过/proc查看系统运行信息
        - [深入理解linux系统下proc文件系统内容](http://www.cnblogs.com/cute/archive/2011/04/20/2022280.html)
        - [使用 /proc 文件系统来访问 Linux 内核的内容](http://www.ibm.com/developerworks/cn/linux/l-proc.html)
    - 观察系统启动的服务
        - `netstat -tulp`: 找出目前系统开启的『网络服务』
        - `netstat -lnp`: 找出所有的有监听网络的服务 (包含 socket 状态)
        - `service --status-all`: 观察所有的服务状态
    - 通过`/etc/init.d`目录下的脚本控制服务
        - 用法：`Usage: /etc/init.d/networking {start|stop|reload|restart|force-reload}`
    - 通过`service`命令控制服务
        - `sudo service [service name] {start|stop|restart|status}`

## Shell基本命令

- `vmstat`: Report virtual memory statistics
- `ps`: 使用PS查看进程信息，了解每一列的含义，掌握其参数
    - 参考 [每天一个linux命令（41）：ps命令](http://www.cnblogs.com/peida/archive/2012/12/19/2824418.html)
- `top`: 使用top查看系统负载，了解每一列的含义
    - 参考 [每天一个linux命令（44）：top命令](http://www.cnblogs.com/peida/archive/2012/12/24/2831353.html)
- `htop`: an interactive process viewer for Linux
    - [Linux下取代top的进程管理工具 htop](http://www.cnblogs.com/mchina/archive/2013/03/15/2858041.html)
    - [htop - an interactive process viewer for Linux](http://hisham.hm/htop/index.php?page=main)
- `kill`: 通过kill给进程发送信号
    - 参考[每天一个linux命令（42）：kill命令](http://www.cnblogs.com/peida/archive/2012/12/20/2825837.html)
    - [Linux进程间通信——使用信号](http://blog.csdn.net/ljianhui/article/details/10128731)
- `lsof`: lsof（list open files）是一个列出当前系统打开文件的工具。在linux环境下，任何事物都以文件的形式存在，通过文件不仅仅可以访问常规数据，还可以访问网络连接和硬件。所以如传输控制协议 (TCP) 和用户数据报协议 (UDP) 套接字等，系统在后台都为该应用程序分配了一个文件描述符，无论这个文件的本质如何，该文件描述符为应用程序与基础操作系统之间的交互提供了通用接口。因为应用程序打开文件的描述符列表提供了大量关于这个应用程序本身的信息，因此通过lsof工具能够查看这个列表对系统监测以及排错将是很有帮助的。
    - 参考[每天一个linux命令（51）：lsof命令](http://www.cnblogs.com/peida/archive/2013/02/26/2932972.html)


# Basic Network Management

## 目标

- 查看网络状态与基本网络管理

## Basic Network Management

- 概念
    - [基础网络概念](http://vbird.dic.ksu.edu.tw/linux_server/0110network_basic.php)
    - 网络协议的层次结构
        - 参考[互联网协议入门（一）](http://www.ruanyifeng.com/blog/2012/05/internet_protocol_suite_part_i.html)
        - 参考[互联网协议入门（二）](http://www.ruanyifeng.com/blog/2012/06/internet_protocol_suite_part_ii.html)
        - 参考[TCP IP网络协议图](./file/TCP-IP_Network_Protocol_Diagram.pdf)
    - IP协议，IP地址的分类，子网掩码
        - [如何理解ip路由和操作linux的路由表](http://linux.chinaunix.net/techdoc/net/2008/09/18/1033149.shtml)
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
    - [iptables vs route](http://superuser.com/questions/419659/iptables-vs-route)
    - [NAT - Network Address Translation](http://www.karlrupp.net/en/computer/nat_tutorial)

## Shell命令

- `ifconfig`
    - 参考[每天一个linux命令（52）：ifconfig命令](http://www.cnblogs.com/peida/archive/2013/02/27/2934525.html)
    - 参考[Linux and Unix - ifconfig command](http://www.computerhope.com/unix/uifconfi.htm)
- `telnet`
    - 参考[Linux and Unix - telnet command](http://www.computerhope.com/unix/utelnet.htm)
- `ping`: use ICMP
    - 参考[ping结果中TTL是什么意思](http://www.ezloo.com/2007/05/ping_ttl.html)
    - 参考[ping 命令详解](http://zhidao.baidu.com/question/13855241.html)
- `traceroute`: traces a route over the internet
    - 参考[每天一个linux命令（55）：traceroute命令](http://www.cnblogs.com/peida/archive/2013/03/07/2947326.html)
- `mtr`: 'traceroute' and 'ping' in a single tool
    - 参考[mtr命令详解](http://xukaizijian.blog.163.com/blog/static/1704331192011023259812/)
- `nslookup`, `host`, `dig`: DNS lookup utility
    - 参考[Linux and Unix - nslookup command](http://www.computerhope.com/unix/unslooku.htm)
    - 参考[Linux and Unix - host command](http://www.computerhope.com/unix/host.htm)
    - 参考[Linux and Unix - dig command](http://www.computerhope.com/unix/dig.htm)
- `whois`: look up information about a internet site
    - 参考[Linux and Unix - whois command](http://www.computerhope.com/unix/uwhois.htm)
    - [站长之家 - whois查询](http://whois.chinaz.com/)
    - [Godaddy whois查询](https://who.godaddy.com/)
- `netstat`:
    - 参考[每天一个linux命令（56）：netstat命令](http://www.cnblogs.com/peida/archive/2013/03/08/2949194.html)
- `ip`
    - 参考[Linux and Unix - ip command](http://www.computerhope.com/unix/ip.htm)
- `iptables`: iptables is a user-space application program that allows a system administrator to configure the tables provided by the Linux kernel firewall (implemented as different Netfilter modules) and the chains and rules it stores. Different kernel modules and programs are currently used for different protocols; iptables applies to IPv4, ip6tables to IPv6, arptables to ARP, and ebtables to Ethernet frames.
    - 参考[百度百科-iptables](http://baike.baidu.com/view/504557.htm#1_1)
    - 参考[wikipedia - iptables](https://en.wiki2.org/wiki/Iptables)


# Writing Shell Scripts

## 目标

- Shell的基本概念及启动过程
- 编写Shell脚本
- 参考
    - [Gnu Bash Reference](http://www.gnu.org/software/bash/manual/bashref.html)
    - [The art of command line](https://github.com/jlevy/the-art-of-command-line)
    - [Awesome Shell](https://github.com/alebcay/awesome-shell)

## 基本概念

### 交互式shell和非交互式shell、登录shell和非登录shell的区别

> 本节内容主要参考[交互式shell和非交互式shell、登录shell和非登录shell的区别](http://smilejay.com/2012/10/interactive-shell-login-shell/)

首先，这是两个不同的维度来划分的，一个是是否交互式，另一个是是否登录。

交互式模式就是在终端上执行，shell等待你的输入，并且立即执行你提交的命令。这种模式被称作交互式是因为shell与用户进行交互。
这种模式也是大多数用户非常熟悉的：登录、执行一些命令、退出。当你退出后，shell也终止了。
shell也可以运行在另外一种模式：非交互式模式，以shell script(非交互)方式执行。
在这种模式下，shell不与你进行交互，而是读取存放在文件中的命令，并且执行它们。当它读到文件的结尾EOF，shell也就终止了。

可以通过打印“$-”变量的值（代表着当前shell的选项标志），查看其中的“i”选项（表示interactive shell）来区分交互式与非交互式shell。

```bash
$ echo $-
himBH

$ ./test.sh
echo $-
hB
```

- 登录shell：是需要用户名、密码登录后才能进入的shell（或者通过”–login”选项生成的shell）。
- 非登录shell：当然就不需要输入用户名和密码即可打开的Shell，例如：直接命令“bash”就是打开一个新的非登录shell，在Gnome或KDE中打开一个“终端”（terminal）窗口程序也是一个非登录shell。
- 执行exit命令，退出一个shell（登录或非登录shell）；
- 执行logout命令，退出登录shell（不能退出非登录shell）。

```bash
$ bash --login
$ logout
$ bash --login
$ exit
logout
 
$ bash
$ logout
bash: logout: not login shell: use `exit'
$ exit
exit
```

bash是 login shell 时，其进程名为”-bash“ 而不是”bash”。 比如下面的命令行演示：
man bash: A login shell is one whose first character of argument zero is a -, or one started with the –login option.

```bash
# 在 login shell 中：
$ echo $0
-bash
$ ps -ef | grep '\-bash' | grep -v grep
root     16823 16821  0 May06 pts/0    00:00:00 -bash
perf     21135 21134  0 May07 pts/1    00:00:00 -bash
 
# 在一个非登陆shell中：
$ echo $0
/bin/bash
$ ps -ef | grep '\-bash' | grep -v grep
$
```

对于Bash来说，登录shell（包括交互式登录shell和使用“–login”选项的非交互shell），它会首先读取和执行`/etc/profile`全局配置文件中的命令，然后依次查找`~/.bash_profile`、`~/.bash_login` 和 `~/.profile`这三个配置文件，读取和执行这三个中的第一个存在且可读的文件中命令。除非被“–noprofile”选项禁止了。

在非登录shell里，只读取`~/.bashrc`（和`/etc/bash.bashrc`、`/etc/bashrc`）文件，不同的发行版里面可能有所不同，如RHEL6.3中非登录shell仅执行了`~/.bashrc`文件（没有执行`/etc/bashrc`），而KUbuntu10.04中却依次执行了`/etc/bash.bashrc` 和 `~/.bashrc` 文件。

对于这些规则，可以直接在相应的配置文件中加一些echo命令来验证其真实性。


### 如何让你的shell脚本更健壮和更可靠

请阅读：

- [Use the Unofficial Bash Strict Mode (Unless You Looove Debugging)](http://redsymbol.net/articles/unofficial-bash-strict-mode/)
- [How "Exit Traps" Can Make Your Bash Scripts Way More Robust And Reliable](http://redsymbol.net/articles/bash-exit-traps/) 

### 语法

#### 常用系统变量

- `$0`: 当前shell程序的名字
- `$1`~`$9`: 命令行上的第一到第九个参数
- `$#`: 命令行上的参数个数
- `$*`: 命令行上的所有参数
- `$@`: 分别用双引号引用命令行上的所有参数
- `$$`: 当前进程的进程标识号(PID)
- `$?`: 上一条命令的退出状态
- `$!`: 最后一个后台进程的进程标识号

#### Builtin commands that are symbols

- `()`: subshell
- `$()`: command substitution
- `(())`: arithmetic evaluation
- `$(())`: arithmetic expansion
- `[]`: test command
- `[[]]`: conditional expression


#### Control Structures

```bash
#----------------------------------
# if...else pattern
#
# if test-command
#    then
#        commands
# fi
#----------------------------------

# check arguments amounts
if [ $# -eq 0 ]
    then
        echo "You must supply at least one argument."
        exit 1
fi
echo "Program running..."

# check whether file is an ordinary file
if [ -f "$1" ]
    then
        echo "$1 is an ordinary file in the working directory"
    else
        echo "$1 is NOT an ordinary file in the working directory"
fi

#----------------------------------
# if...then...else pattern
# 
# if test-command
#    then
#        commands
#    else
#        commands
# fi
#----------------------------------

$ cat out
if [ $# -eq 0 ]
    then
        echo "Usage: out [-v] filenames..." 1>&2
        exit 1
fi

if [ "$1" = "-v" ]
    then
        shift
        less -- "$@"
    else
        cat -- "$@"
fi

#----------------------------------
# if...then...elif pattern
# 
# if test-command
#    then
#        commands
#    elif test-command
#    then
#        commands
#    ...
#    else
#        commands
# fi
#----------------------------------

$ cat if3
echo -n "word 1: "
read word1
echo -n "word 2: "
read word2
echo -n "word 3: "
read word3
if [ "$word1" = "$word2" -a "$word2" = "$word3" ]
    then
        echo "Match: words 1, 2, & 3"
    elif [ "$word1" = "$word2" ]
    then
        echo "Match: words 1 & 2"
    elif [ "$word1" = "$word3" ]
    then
        echo "Match: words 1 & 3"
    elif [ "$word2" = "$word3" ]
    then
        echo "Match: words 2 & 3"
    else
        echo "No Match"
fi

#----------------------------------
# for...in pattern
# 
# for loop-index in argument-list
# do
#     commands
# done
#----------------------------------

$ cat fruit
for fruit in apples oranges pears bananas
do
    echo "$fruit"
done
echo "Task complete."

$ cat dirfiles
for i in *
do
    if [ -d "$i" ]
        then
            echo "$i"
    fi
done


#----------------------------------
# for pattern: the loop-index takes on the value of each of the command- line arguments, one at a time. 
# 
# for loop-index
# do
#     commands
# done
#----------------------------------

$ cat whos
#!/bin/bash

if [ $# -eq 0 ]
    then
        echo "Usage: whos id..." 1>&2
        exit 1
fi

for id
do
    mawk -F: '{print $1, $5}' /etc/passwd |
    grep -i "$id"
done

#----------------------------------
# while pattern 
# 
# while test-command
# do
#     commands
# done
#----------------------------------

$ cat count
#!/bin/bash
number=0
while [ "$number" -lt 10 ]
do
    echo -n "$number"
    ((number +=1))
done
echo

#----------------------------------
# until pattern 
# 
# until test-command
# do
#     commands
# done
#----------------------------------

$ cat until1
secretname=zach
name=noname
echo "Try to guess the secret name!"
echo
until [ "$name" = "$secretname" ]
do
    echo -n "Your guess: "
    read name
done
echo "Very good."


#----------------------------------
# break and continue pattern 
# 
# until test-command
# do
#     commands
# done
#----------------------------------

$ cat brk
for index in 1 2 3 4 5 6 7 8 9 10
do
    if [ $index -le 3 ] ; then
        echo "continue"
        continue
    fi

    echo $index

    if [ $index -ge 8 ] ; then
        echo "break"
        break
    fi
done


#----------------------------------
# case pattern 
# 
# case test-string in
#     pattern-1)
#         commands-1
#         ;;
#     pattern-2)
#         commands-2
#         ;;
#     pattern-3)
#         commands-3
#         ;; 
# ...
# esac
#----------------------------------

$ cat case1
echo -n "Enter A, B, or C: "
read letter
case "$letter" in
    A)
        echo "You entered A"
        ;;
    B)
        echo "You entered B"
        ;;
    C)
        echo "You entered C"
        ;;
    *)
        echo "You did not enter A, B, or C"
        ;;
esac

$ cat case2
echo -n "Enter A, B, or C: "
read letter
case "$letter" in
    a|A)
        echo "You entered A"
        ;;
    b|B)
        echo "You entered B"
        ;;
    c|C)
        echo "You entered C"
        ;;
    *)
        echo "You did not enter A, B, or C"
        ;;
esac

#----------------------------------
# select pattern 
# 
# select varname [in arg...]
# do
#     commands
# done
#----------------------------------

$ cat fruit2
#!/bin/bash
PS3="Choose your favorite fruit from these possibilities: "
select FRUIT in apple banana blueberry kiwi orange watermelon STOP
do
    if [ "$FRUIT" == "" ]; then
        echo -e "Invalid entry.\n"
        continue
    elif [ $FRUIT = STOP ]; then
        echo "Thanks for playing!"
        break
    fi
    
    echo "You chose $FRUIT as your favorite."
    echo -e "That is choice number $REPLY.\n"
done
```

#### File Descriptors

```bash
$ cat sortmerg
#!/bin/bash
usage ()
{
    if [ $# -ne 2 ]; then
        echo "Usage: $0 file1 file2" 2>&1
        exit 1
    fi
}

# Default temporary directory
: ${TEMPDIR:=/tmp}

# Check argument count
usage "$@"

# Set up temporary files for sorting
file1=$TEMPDIR/$$.file1
file2=$TEMPDIR/$$.file2

# Sort
sort $1 > $file1
sort $2 > $file2

# Open $file1 and $file2 for reading. Use file descriptors 3 and 4.
exec 3<$file1
exec 4<$file2

# Read the first line from each file to figure out how to start.
read Line1 <&3
status1=$?
read Line2 <&4
status2=$?

# Strategy: while there is still input left in both files:
# Output the line that should come first.
# Read a new line from the file that line came from.
while [ $status1 -eq 0 -a $status2 -eq 0 ]
do
    if [[ "$Line2" > "$Line1" ]]; then
            echo -e "1.\t$Line1"
            read -u3 Line1
            status1=$?
        else
            echo -e "2.\t$Line2"
            read -u4 Line2
            status2=$?
    fi
done

# Now one of the files is at end-of-file.
# Read from each file until the end.
# First file1:
while [ $status1 -eq 0 ]
do
    echo -e "1.\t$Line1"
    read Line1 <&3
    status1=$?
done

# Next file2:
while [[ $status2 -eq 0 ]] do
       echo -e "2.\t$Line2"
       read Line2 <&4
       status2=$?
done

# Close and remove both input files
exec 3<&- 4<&-
rm -f $file1 $file2
exit 0
```

## Shell命令

- `export`
- `source`
- `xargs`: construct argument list(s) and execute utility
    - [Example xargs](http://examplenow.com/zh-cn/xargs/man1)
    - [10 Xargs Command Examples in Linux / UNIX](http://www.thegeekstuff.com/2013/12/xargs-examples/)


# Schedule Tasks

## 目标

- 掌握cron
- 掌握anacron
- 掌握at

## 内容

### 参考

- PG2UL，page 605，Scheduling Tasks
- [crontab 定时任务](http://linuxtools-rst.readthedocs.org/zh_CN/latest/tool/crontab.html)
- [linux Crontab 使用](http://www.oschina.net/questcion/234345_42400)
- [使用 Anacron 处理 Linux 关机问题](http://www.ibm.com/developerworks/cn/linux/l-anacron/index.html)
- [linux定时任务的设置](http://www.blogjava.net/freeman1984/archive/2010/09/23/332715.html)

### cron的坑

- crontab文件设置了任务的执行时间，此时间依赖当前os的系统时区。

### cron和anacron的区别

cron是用来控制循环执行的例行性工作的，可循环的时间为分钟、小时、每周、每月或每年等。比如我要设定机器每天早上8点进行备份，就可以用到这个服务。
除非我们的机器保持每天都24小时开始，否则就会有些系统例行工作都没有人做了，这个时候就可以用到anacron了。

anacron并不是用来取代cron的，anacron存在的目的就在于我们上面提到的，在处理非 24 小时一直启动的Linux系统的cron服务的执行！
所以 anacron 并不能指定何时执行某项任务，而是以天为单位或者是在开机后立刻进行anacron的动作，他会去侦测停机期间应该进行但是并没有进行的cron服务，
如果有就将该任务执行一遍，然后就自动停止。anacron脚本不会在OS使用电池作为电源时候运行。

### Crontab文件

共有两种类型的 Cron 作业（即由 Cron 运行的程序）：系统 Cron 作业，由系统运行，执行系统维护任务；另一种是 用户 Cron 作业，由用户创建，用于执行用户任务。
对于这两种作业而言，系统 Cron 作业更加重要一些。这些作业可能包括清除 /tmp 中的陈旧文件、替换日志文件、更新垃圾邮件过滤规则，以及更新 locate 数据库。

cron守护进程根据crontab文件中的配置执行定时任务。

- 系统crontab文件保存在`/etc/cron.d`目录和`/etc/crontab`文件中
- 用户可以使用`crontab`工具设置个人的crontab文件，用户的crontab文件保存在`/var/spool/cron/crontabs`中

#### 系统crontab文件

crontab文件设置命令的执行频率。

`/etc/crontab`内容如下：

```bash
# /etc/crontab: system-wide crontab
# Unlike any other crontab you don't have to run the `crontab'
# command to install the new version when you edit this file
# and files in /etc/cron.d. These files also have username fields,
# that none of the other crontabs do.

SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin

# m h dom mon dow user	command
17 *	* * *	root    cd / && run-parts --report /etc/cron.hourly
25 6	* * *	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.daily )
47 6	* * 7	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.weekly )
52 6	1 * *	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.monthly )
```

最后4行命令的格式如下：

> minute hour day-of-month month day-of-week user command

The first five fields indicate when cron will execute the command: 

- The **minute** is the number of minutes after the start of the hour
- the **hour** is the hour of the day based on a 24-hour clock
- the **day-of-month** is a number from 1 to 31
- the **day-of-week** is a number from 0 to 7, with 0 and 7 indicating Sunday
- An asterisk (*) substitutes for any value in a field
- The user is the username or user ID of the user that the command will run as

除了`/etc/crontab`，cron守护进程还会读取`/etc/cron.d`下的配置文件。下面是`/etc/cron.d/anacron`的内容，
这段配置告知`cron`每天7:30 AM运行`anacron`初始化脚本。这段初始化脚本只会在系统开机且不使用电池电源的时候运行`anacron`。

```bash
# /etc/cron.d/anacron: crontab entries for the anacron package

SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin

30 7    * * *   root	start -q anacron || :
```

#### 用户crontab文件

- 用户crontab文件保存在`/var/spool/cron/crontabs/`目录下，并且以用户名命令
- 可以通过`crontab -l`查看当前用户的crontab文件
- 可以通过`crontab -e`创建或者编辑当前用户的crontab文件
- 可以通过`crontab -r`删除当前用户的crontab文件

### anacron配置文件

Anacron 通过 /etc/anacrontab 文件进行控制。该文件可以包含注释行（使用一个前导散列符号 # 表示）、环境变量分配（比如 SHELL=/bin/bash）和作业定义。

`/etc/anacrontab`中的内容如下：

```bash
# /etc/anacrontab: configuration file for anacron

# See anacron(8) and anacrontab(5) for details.

SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin
HOME=/root
LOGNAME=root

# These replace cron's entries
1	5	cron.daily	run-parts --report /etc/cron.daily
7	10	cron.weekly	run-parts --report /etc/cron.weekly
@monthly	15	cron.monthly	run-parts --report /etc/cron.monthly
```

最后三行记录的格式如下：

> period delay identifier command

- period是anacron执行命令的频率，单位为天
- delay是anacron启动后，多长时间执行命令，单位为分钟
- identifier是anacron用来记录上次什么时候执行命令的文件的文件名，文件保存在`/var/spool/anacron`文件夹下


# Futher Reading

## Knowledge

- [Linux Tools Quick Tutorial](http://linuxtools-rst.readthedocs.org/zh_CN/latest/index.html)
- [每天一个linux命令目录](http://www.cnblogs.com/peida/archive/2012/12/05/2803591.html)

## Utilites

- [Explain Shell](http://explainshell.com/)




# FAQ

## 如何安装中文语言支持（System Settings -> Language Support）及中文输入法（System Settings -> Text Entry）

[Ubuntu上的输入法情况](http://wiki.ubuntu.org.cn/%E4%B8%AD%E6%96%87%E8%BE%93%E5%85%A5%E6%B3%95):

> Ubuntu上有IBus、Fcitx等开源的输入法框架，支持各种各样的引擎。  
> Rime（中州韵输入法引擎）是一种流行的开源跨平台输入法，支持IBus和Fcitx框架。  
> 搜狗输入法在2014年4月发布了Linux版本，使用Fcitx框架。  
> 免费但不开源的小小输入法，也提供对Ubuntu的支持。  
> 作为Chrome扩展的输入法：Google Input Tools  
> 作为Firefox扩展的输入法：火输(Fireinput)。  
> 可以直接在浏览器中使用的云输入法：搜狗云输入法、QQ云输入法等。

目前比较推荐Linux上的搜狗输入法：[下载地址](http://pinyin.sogou.com/linux/?r=pinyin)

搜过拼音的安装方法：

- [Ubuntu 14.04安装搜狗拼音linux版应该注意的问题](http://blog.csdn.net/tao_627/article/details/24119037)
- [Ubuntu下安装搜狗拼音输入法](http://blog.csdn.net/rflyee/article/details/9472579)

## 如何升级系统，安装最新的补丁和最新版本的软件

GUI操作

1. System Settings -> Softwares&Updates -> Select best download server，选择最佳的软件更新服务器
1. 然后按Alt+F2组合键调出运行命令框，然后键入`update-manager -d`，然后升级系统

终端操作

1. 执行下面的命令，安装最新的系统补丁：`sudo apt-get update && sudo apt-get dist-upgrade`

## 修改Ubuntu Software Repository的下载地址，比如把下载地址改为国内的repository服务地址

参考：

1. GUI操作参考[Linux开发环境搭建与使用——ubuntu更新设置](http://blog.csdn.net/tennysonsky/article/details/44221433)
1. Bash操作参考：[Repositories/CommandLine](https://help.ubuntu.com/community/Repositories/CommandLine)

Ubuntu uses apt for package management. Apt stores a list of repositories or software channels in the file

```bash
/etc/apt/sources.list
```

and in any file with the suffix .list under the directory

```bash
/etc/apt/sources.list.d/
```

See `man sources.list` for more about this storage mechanism.

By editing these files from the command line, we can add, remove, or temporarily disable software repositories.

## 如何给Ubuntu Linux Virutal Machine安装VMWare Tools

- 安装方法参考
    - [Installing VMware Tools in an Ubuntu virtual machine (1022525)](http://kb.vmware.com/selfservice/microsites/search.do?cmd=displayKC&docType=kc&externalId=1022525)
- 卸载方法参考
    - [Uninstalling and manually installing VMware Tools in VMware Fusion (1014522)](http://kb.vmware.com/selfservice/microsites/search.do?cmd=displayKC&docType=kc&externalId=1014522&sliceId=1&docTypeID=DT_KB_1_1&dialogID=672738403&stateId=1%200%20672744194)
    - [VMware Tools Uninstaller in Ubuntu Guest Does Not Remove vmxnet Module (1004351)](http://kb.vmware.com/selfservice/microsites/search.do?cmd=displayKC&docType=kc&externalId=1004351&sliceId=1&docTypeID=DT_KB_1_1&dialogID=672738403&stateId=1%200%20672744194)

## 如何给Ubuntu Linux Virtual Machine安装Parallel Tools

参考[How do I install Parallels Tools in Ubuntu Virtual Machine?](http://kb.parallels.com/en/113394)

## 给Ubuntu安装SSH服务

ubuntu默认并没有安装ssh服务，如果通过ssh链接ubuntu，需要自己手动安装ssh-server。

- [Ubuntu Document - OpenSSH 服务器](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
- [ubuntu下如何安装使用SSH？](http://os.51cto.com/art/201109/291634.htm)

## 使用命令`man wget > man-wget.txt`把命令文档输入到文本文件后，打开man-wget.txt，发现有很多重复字符，或者乱码？

将man手册查询命令输出到文本文件中，要求过滤掉控制字符^H（Backspace (退格)）  

`man chmod |col –b >/home/man_chmod.txt`

col命令的使用方法见[col命名详解](http://myblog.jyc.edu.cn/?p=62)

## 如何修改OS的hostname

参考[How do I change the hostname without a restart?](http://askubuntu.com/questions/87665/how-do-i-change-the-hostname-without-a-restart)

`hostname`临时保存在内存，永久保存在`/etc/hostname`文件中，同时`/etc/hosts`文件中也配置了`hostname`对应的IP地址

- 查看主机名`hostname`
- 临时修改主机名，命令执行后即时生效`sudo hostname [yourhostname]`，重启后依然恢复原hostname
- 永久修改主机名，将新的主机名写入，重启系统后生效`sudo vim /etc/hostname`
- `hostnamectl`命令包含了临时修改hostname和修改`/etc/hostname`两种操作，但是不会修改`/etc/hosts`，所以执行`hostnamectl`命令后还需要手动修改`/etc/hosts`文件  

```bash
hostnamectl set-hostname new-hostname
```

## 设置DNS服务的服务地址

编辑保存DNS信息的配置文件

```bash
sudo pico /etc/resolv.conf
```

最多可以使用3个DNS地址，内容如下

```bash
nameserver xxx.xxx.xxx.xxx  nameserver xxx.xxx.xxx.xxx  nameserver xxx.xxx.xxx.xxx
```

对resolv.conf文件的修改是即时生效的，可以使用nslookup命令进行查询。

## 如何配置网卡和IP地址

ubuntu的网络配置信息放在`/etc/network/interfaces`中，

```bash
sudo vim /etc/network/interfaces
```

要通过dhcp获取ip，则添加如下内容：

```bash
auto eth0
iface eth0 inet dhcp
```

如果配置静态ip，则添加如下内容：

```bash
auto eth0
iface eth0 inet static
    address 192.168.1.201
    netmask 255.255.255.0
    gateway 192.168.1.1
```

需重启下网络服务使配置生效

```bash
sudo /etc/init.d/networking restart
```
## 如何从Internet更新ubuntu本地的时间？

You can do so with `sudo ntpdate time.nist.gov` other servers include time.windows.com, etc.
http://www.pool.ntp.org/ lists time servers around the world.

## 切换网络后，如何强制更新网卡IP？

To renew or release an IP address for the eth0 interface, enter:

```bash
$ sudo dhclient -r eth0
$ sudo dhclient eth0
```
