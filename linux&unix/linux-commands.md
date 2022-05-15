- [1. 网络](#1-网络)
- [2. 数据传输](#2-数据传输)
- [3. 文档处理](#3-文档处理)
- [4. CPU](#4-cpu)
- [5. 内存](#5-内存)
- [6. 进程](#6-进程)
- [7. 磁盘管理](#7-磁盘管理)
- [8. 性能优化](#8-性能优化)
- [9. 安全](#9-安全)
- [10. 专题](#10-专题)
- [11. 参考](#11-参考)


# 1. 网络

- netstat: 多种网络栈和接口统计信息
- ifconfig: 多种网络栈和接口统计信息
- iftop: 
- ss: 获取socket统计信息，优势在于它能够显示更多更详细的有关TCP和连接状态的信息，而且比netstat更快
  - [man page](https://man7.org/linux/man-pages/man8/ss.8.html)
  - [How to Use the ss Command on Linux](https://www.howtogeek.com/681468/how-to-use-the-ss-command-on-linux/)
  - [Probe Your Linux Sockets With ss](https://www.linux.com/learn/intro-to-linux/2017/4/probe-your-linux-sockets-ss)
- ip: 网络接口统计信息
- iptables: a [user-space](https://en.wikipedia.org/wiki/User_space) utility program that allows a [system administrator](https://en.wikipedia.org/wiki/System_administrator) to configure the [IP packet filter rules](https://en.wikipedia.org/wiki/Packet_filter) of the [Linux kernel](https://en.wikipedia.org/wiki/Linux_kernel) [firewall](https://en.wikipedia.org/wiki/Firewall_(computing))
  - [Iptables详解](https://blog.csdn.net/reyleon/article/details/12976341)
  - https://en.wikipedia.org/wiki/Iptables
  - https://www.netfilter.org/documentation/index.html
  - https://www.frozentux.net/iptables-tutorial/iptables-tutorial.html
  - https://wiki.archlinux.org/title/iptables
- ping: 测试网络连通性
- traceroute: 测试网络路由
- mtr: 网络联通性判断工具，它可以结合 ping nslookup tracert 来判断网络的相关特性
  - [mtr的用法](https://mp.weixin.qq.com/s/90rHRd8ZjrWc6pv6H1gYtQ)
- pathchar: 确定网络路径特征
- tcpdump: 网络数据包嗅探器
  - [home web site of tcpdump](https://www.tcpdump.org/)
  - [Let's learn tcpdump!](https://jvns.ca/tcpdump-zine.pdf)
  - [tcpdump命令详解](https://www.cnblogs.com/ggjucheng/archive/2012/01/14/2322659.html)
- ngrep: grep命令的网络版，用于搜寻指定的数据包
  - [github.com/jpr5/ngrep](https://github.com/jpr5/ngrep)
  - [ngrep - wikipedia](https://en.wikipedia.org/wiki/Ngrep)
  - [What is ngrep and How to Use It?](https://linuxhint.com/how-to-use-ngrep/)
  - [ngrep - network grep ](http://ngrep.sourceforge.net/usage.html)
- tcpkit: 支持用 lua 脚本分析网络数据包的工具，附带简单协议解析(Redis/Memcached)和延时统计
  - https://github.com/git-hulk/tcpkit
- wireshark: a popular open source graphical user interface (GUI) tool for analyzing packets
  - [Wireshark基本介绍和学习TCP三次握手](https://www.cnblogs.com/TankXiao/archive/2012/10/10/2711777.html)
  - [Wireshark 的抓包和分析，看这篇就够了！](https://mp.weixin.qq.com/s/poo59EGr-V6hC84goESaiA)
  - [【技术流】Wireshark对HTTPS数据的解密](https://zhuanlan.zhihu.com/p/36669377)
  - [Decrypting SSL/TLS Traffic with Wireshark](https://linuxhint.com/decrypt-ssl-tls-wireshark/)
- tshark: tshark是wireshark网络分析工具下的一个分支，主要用于命令行环境进行抓包、分析，尤其对协议深层解析时，tcpdump难以胜任的场景中
  - [tshark.dev](https://tshark.dev/)complete guide to working with packet captures on the command-line
  - [网络分析利器wireshark命令版(1)：tshark简介](https://segmentfault.com/a/1190000018886363)
  - [网络分析利器wireshark命令版(2)：tshark使用示例](https://segmentfault.com/a/1190000018886731)
  - [Use Wireshark at the Linux command line with TShark](https://opensource.com/article/20/1/wireshark-linux-tshark)


# 2. 数据传输

- rsync
  - [官方文档](https://rsync.samba.org/documentation.html)
  - [rsync udr——远程大文件传输加速](https://mp.weixin.qq.com/s?__biz=MzUxMDQxMDMyNg==&mid=2247484620&idx=1&sn=ea286199de2572391194428bb58909b5&chksm=f9022ff5ce75a6e3442ccbc4a9e1cadf10c56d760f8fbef0434297d9bd4ddc4152c3ebb33da9&scene=21#wechat_redirect)
  - [Running rsync as a daemon](https://www.jveweb.net/en/archives/2011/01/running-rsync-as-a-daemon.html)
  - [centos下安装rsync](https://www.jianshu.com/p/0df0633613d8)
  - [Rsync : Sync Files/Directories](https://www.server-world.info/en/note?os=CentOS_7&p=rsync)
- wdt: WDT（Warp speed Data Transfer），多链路数据传输，基于TCP协议；是FaceBook开源的一个项目，其目的是在尽量减少资源（CPU/内存等）消耗的情况下，利用多个TCP路径提高两个系统之间传送文件的效率。
  - [大文件传输利器WDT，跨网、跨国效果非常赞](https://mp.weixin.qq.com/s/uRHsnckaAtJ_nEHyLFyGgw)
- curl
  - [Documentation](https://curl.se/docs/)
  - [The Art Of Scripting HTTP Requests Using Curl](https://curl.se/docs/httpscripting.html)
  - [阮一峰——curl网站开发指南](http://www.ruanyifeng.com/blog/2011/09/curl.html)


# 3. 文档处理

- find
  - [Classic SysAdmin: How to Search for Files from the Linux Command Line](https://www.linuxfoundation.org/blog/classic-sysadmin-how-to-search-for-files-from-the-linux-command-line/)
  - [Beyond Finding Stuff with the Linux find Command](https://www.linux.com/topic/desktop/beyond-finding-stuff/)
  - [find命令 – 根据路径和条件搜索指定文件](https://www.linuxcool.com/find)
  - [How to audit permissions with the find command](https://www.redhat.com/sysadmin/audit-permissions-find)
- jq: jq is a lightweight and flexible command-line JSON processor.
  - [tutorial](https://stedolan.github.io/jq/tutorial/)
- xargs
  - [xargs 命令教程](https://www.ruanyifeng.com/blog/2019/08/xargs-tutorial.html)
- grep
  - [Linux grep 命令](https://www.runoob.com/linux/linux-comm-grep.html)
  - [Linux中的Grep命令使用实例](https://cloud.tencent.com/developer/article/1554542)
- ack
  - [Linux: Ack 用法, Ack 文档](https://justcode.ikeepstudying.com/2020/10/linux-ack-%E7%94%A8%E6%B3%95-ack-%E6%96%87%E6%A1%A3/)
  - [官方文档](https://beyondgrep.com/documentation/)
- awk
  - [awk 入门教程](http://www.ruanyifeng.com/blog/2018/11/awk.html)
  - [AWK 简明教程](https://coolshell.cn/articles/9070.html)
  - [The GNU Awk User’s Guide](https://www.gnu.org/software/gawk/manual/gawk.html)
  - [30 Examples for Awk Command in Text Processing](https://likegeeks.com/awk-command/)
  - [How To Use the AWK language to Manipulate Text in Linux](https://www.digitalocean.com/community/tutorials/how-to-use-the-awk-language-to-manipulate-text-in-linux?utm_source=DigitalOcean_Newsletter)
  - [Why you should learn just a little Awk](https://gregable.com/2010/09/why-you-should-know-just-little-awk.html)
- sed
  - [SED 简明教程](https://coolshell.cn/articles/9104.html)
  - [Sed - An Introduction and Tutorial by Bruce Barnett](https://www.grymoire.com/Unix/Sed.html)
  - [Intermediate Sed: Manipulating Streams of Text in a Linux Environment](https://www.digitalocean.com/community/tutorials/intermediate-sed-manipulating-streams-of-text-in-a-linux-environment)



# 4. CPU


- top
  - [理解CPU利用率](https://www.jianshu.com/p/f595ee986b55?hmsr=toutiao.io&utm_medium=toutiao.io&utm_source=toutiao.io)
  - [30 Top Command Examples for Monitoring in Linux](https://linoxide.com/linux-command/linux-top-command-examples-screenshots/)
  - [How Do I Find Out Linux CPU Utilization?](https://www.cyberciti.biz/tips/how-do-i-find-out-linux-cpu-utilization.html)
  - [top命令](https://www.cnblogs.com/peida/archive/2012/12/24/2831353.html)
  - [每天一个linux命令（44）：top命令](https://www.cnblogs.com/peida/archive/2012/12/24/2831353.html)
- htop
- sysstat
- mpstat
- sar: 系统活动报告工具，可以观测当前活动并且能配置为保存和报告历史统计数据



# 5. 内存

- vmstat: Virtual Meomory Statistics(虚拟内存统计), 可对操作系统的虚拟内存、进程、CPU活动进行监视. 它是对系统的整体情况进行统计, 但不能针对某个进程进行深入分析
  - [vmstat 命令](https://blogread.cn/it/article/3902?f=wb_news)


# 6. 进程

- lsof: 用于查看进程开打的文件，打开文件的进程，进程打开的端口(TCP、UDP)
  - `man lsof`
  - [lsof 命令使用指南](https://mp.weixin.qq.com/s?__biz=MzI3MTI2NzkxMA==&mid=2247486509&idx=1&sn=942d2f3ad6d18db2e0db02ef8b03a7c2&chksm=eac52d04ddb2a412c970acef315b1ce41243ff953cdd500b8260639c943a3d0c467fbefce8a1&scene=21#wechat_redirect)
- ps
- pstree
- kill
- ulimit: provides control over the resources available to the shell and to processes started by it, on systems that allow such control
  - https://phoenixnap.com/kb/ulimit-linux-command
  - https://ss64.com/bash/ulimit.html
- prlimit: get and set process resource limits
  - https://manpages.ubuntu.com/manpages/xenial/man1/prlimit.1.html
- pgrep
- fg/bg
  - [Linux - 请允许我静静地后台运行](http://blog.jobbole.com/111850/)


# 7. 磁盘管理

- df/du
  - [Linux下查看文件和文件夹大小的df和du命令](https://yayu.org/look.php?id=162)
- iostat: 收集和展示系统输入和输出存储设备统计的简单工具
- iotop: 监控和显示实时的磁盘 I/O 输入和输出和程序进程

# 8. 性能优化

- perf: TCP/IP栈跟踪：连接、数据包、丢包、延时
  - [perf Examples](https://www.brendangregg.com/perf.html)
  - [How to use perf tool for tracing similar to dtrace](https://www.thegeekdiary.com/how-to-use-perf-tool-for-tracing-similar-to-dtrace/)
- DTrace: DTrace is a comprehensive dynamic tracing framework originally created by Sun Microsystems for troubleshooting kernel and application problems on production systems in real time
  - [wiki2 - DTrace](https://wiki2.org/en/DTrace)
  - [DTrace Tools](https://www.brendangregg.com/dtrace.html)
- Berkeley Packet Filter: The Berkeley Packet Filter (BPF) is a technology used in certain computer operating systems for programs that need to, among other things, analyze network traffic (and eBPF is an extended BPF JIT virtual machine in the Linux kernel).
  - [Wiki2 - BPF](https://wiki2.org/en/EBPF+Newton)


# 9. 安全

- nmap
  - [Understanding Nmap by using hping](https://medium.com/@reginaldlaurent/understanding-nmap-by-using-hping-c27e6b613bd9)
  - [Comparison of Nmap, Netcat, Hping3 tools](https://titanwolf.org/Network/Articles/Article?AID=43618944-204a-4ac9-a982-2f163db31e89)
  - [NMAP 常用扫描简介（一）](https://mp.weixin.qq.com/s?__biz=MjM5NjQ4MjYwMQ==&mid=2664608847&idx=1&sn=5d98128987ce41aaf92028aac20383f4&chksm=bdce8f098ab9061f582e37a63c9901783577654f87a240b37372282e911288ce6b671b8180bb&scene=0&key=24d0ae311a85eefa32abe6c5b5c7cf5962630da7717bcaa1e18153031255be627971e084606566e6faf43eee1ea331d68034bf7d276796d8c7941a024ff821eca1880bd757e2aa85ac02acdc8f998da8&ascene=0&uin=MjYxMzYyNzA0MA%3D%3D&devicetype=iMac+MacBookPro11%2C4+OSX+OSX+10.12.4+build(16E195)&version=12020110&nettype=WIFI&fontScale=100&pass_ticket=6Hb1hWILMRJHL9uGhy9pAbkGJHl5duMbl9l1zltmQzBvNtmcDolgjXush5at2jq1)
  - [Linux常用网络工具：批量主机服务扫描之nmap](https://www.linuxdiyf.com/linux/12486.html)
  - [Informative guide to NC (Ncat) command in Linux](https://thelinuxgurus.com/informative-guide-to-nc-ncat-command-in-linux/)



# 10. 专题

- 查看TCP连接数
  - https://my.oschina.net/u/1169079/blog/397705
- 查看网络流量
  - 监控总体带宽使用――nload、bmon、slurm、bwm-ng、cbm、speedometer和netload
  - 监控总体带宽使用（批量式输出）――vnstat、ifstat、dstat和collectl
  - 每个套接字连接的带宽使用――iftop、iptraf、tcptrack、pktstat、netwatch和trafshow
  - 每个进程的带宽使用――nethogs
- [数据科学家的命令行技巧](https://linux.cn/article-10342-1.html)
- [三种系统监控工具对比：top vs Htop vs Glances](https://mp.weixin.qq.com/s/_YdwciFT6qu5_kUIyylR2g)
- 在多个Linux上执行命令
  - https://www.tecmint.com/run-commands-on-multiple-linux-servers/
  - https://serverfault.com/questions/161690/distributed-grep


# 11. 参考

- [Linux工具快速教程](https://linuxtools-rst.readthedocs.io/zh_CN/latest/index.html)
- [Linux命令大全(手册)](https://www.linuxcool.com/)
- [每天一个linux命令目录](https://www.cnblogs.com/peida/archive/2012/12/05/2803591.html)
- 性能优化
  - [Linux Performance](https://www.brendangregg.com/linuxperf.html)
  - [性能之巅：Linux 网络性能分析工具](https://www.infoq.cn/article/linux-networking-performance-analytics/)
  - [性能不好怎么办？对着清单撸一遍](https://mp.weixin.qq.com/s?__biz=MzAwNjY4NTQ4MA==&mid=2651174290&idx=1&sn=288518f030801f4d90878e806546487c&scene=1&srcid=0721NBPW2U9bCAlMyD6IR9uY&from=singlemessage&isappinstalled=0#wechat_redirect)
    - [中文翻译：用十条命令在一分钟内检查Linux服务器性能](http://www.infoq.com/cn/news/2015/12/linux-performance/)
