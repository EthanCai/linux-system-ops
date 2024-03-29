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

设备&路由：

- ip: 用于显示与配置网卡参数。作为Linux系统下一款好用的网卡参数配置工具，ip命令除了常规操作外，还可以对主机的路由、网络设备、策略路由以及隧道信息进行查看。
  - [ip命令 – 显示与配置网卡参数](https://www.linuxcool.com/ip)
  - [16 Linux ip command examples to configure network interfaces (cheatsheet)](https://www.golinuxcloud.com/linux-ip-command/)
  - [https://www.golinuxcloud.com/ip-route-command-in-linux/](https://www.golinuxcloud.com/ip-route-command-in-linux/)
- ifconfig: 显示或设置网络设备参数信息
  - [ifconfig命令 – 显示或设置网络设备参数信息](https://www.linuxcool.com/ifconfig)
- route
  - [第二章、基础网络概念 | 鸟哥的linux私房菜](http://cn.linux.vbird.org/linux_server/0110network_basic_3.php#tcpip_network_route)
  - [第八章、路由观念与路由器设定 | 鸟哥的linux私房菜](http://cn.linux.vbird.org/linux_server/0230router_1.php)
- iptables: a user-space utility program that allows a system administrator to configure the IP packet filter rules of the Linux kernel firewall, implemented as different Netfilter modules. The filters are organized in different tables, which contain chains of rules for how to treat network traffic packets.
  - [Iptables详解](https://blog.csdn.net/reyleon/article/details/12976341)
  - https://en.wikipedia.org/wiki/Iptables
    - ![](./assets/packet-flow-in-netfilter-and-general-networking.png)
  - https://www.netfilter.org/documentation/index.html
    - https://www.frozentux.net/iptables-tutorial/iptables-tutorial.html
  - https://wiki.archlinux.org/title/iptables
  - [iptables vs route](http://superuser.com/questions/419659/iptables-vs-route)
- iftop: 用来监控网卡的实时流量、反向解析IP、显示端口信息
  - [Linux流量监控工具 - iftop (最全面的iftop教程)](https://www.vpser.net/manage/iftop.html)


DNS&连通性：

- DNS lookup utility
  - nslookup
    - 参考[Linux and Unix - nslookup command](http://www.computerhope.com/unix/unslooku.htm)
  - dig
    - 参考[Linux and Unix - dig command](http://www.computerhope.com/unix/dig.htm)
  - host
    - 参考[Linux and Unix - host command](http://www.computerhope.com/unix/host.htm)
- ping: 测试网络连通性
  - [ping命令 – 测试主机间网络连通性](https://www.linuxcool.com/ping)
  - [15+ ping command examples in Linux](https://www.golinuxcloud.com/ping-command-linux)
- traceroute: 追踪数据包在网络上的传输时的全部路径
  - [每天一个linux命令（55）：traceroute命令](https://www.cnblogs.com/peida/archive/2013/03/07/2947326.html)
  - [traceroute命令 – 追踪数据包在网络上的传输时的全部路径](https://www.linuxcool.com/traceroute)
- mtr: 全称 my traceroute，是一个把 ping 和 traceroute 合并到一个程序的网络诊断工具
  - [mtr的用法](https://mp.weixin.qq.com/s/90rHRd8ZjrWc6pv6H1gYtQ)
  - [MTR工具使用说明与结果分析](https://help.aliyun.com/document_detail/98706.html)

状态统计：

- netstat: 显示网络状态，例如网络连接状态、路由表信息、接口状态、NAT、多播成员等等
  - [netstat命令 – 显示网络状态](https://www.linuxcool.com/netstat)
  - [20 netstat command examples in Linux [Cheat Sheet]](https://www.golinuxcloud.com/netstat-command-in-linux/)
- ss: 获取socket统计信息，优势在于它能够显示更多更详细的有关TCP和连接状态的信息，而且比netstat更快
  - [man page](https://man7.org/linux/man-pages/man8/ss.8.html)
  - [How to Use the ss Command on Linux](https://www.howtogeek.com/681468/how-to-use-the-ss-command-on-linux/)
  - [Probe Your Linux Sockets With ss](https://www.linux.com/learn/intro-to-linux/2017/4/probe-your-linux-sockets-ss)
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
  - [Using Grep & Regular Expressions to Search for Text Patterns in Linux](https://www.digitalocean.com/community/tutorials/using-grep-regular-expressions-to-search-for-text-patterns-in-linux)
  - [How To Use grep Command In Linux / UNIX With Practical Examples](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/)
    - [Regular expressions in grep ( regex ) with examples](https://www.cyberciti.biz/faq/grep-regular-expressions/)
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

- sar: System Activity Reporter（系统活动情况报告）的缩写。sar工具将对系统当前的状态进行取样，然后通过计算数据和比例来表达系统的当前运行状态。它的特点是可以连续对系统取样，获得大量的取样数据；取样数据和分析的结果都可以存入文件，所需的负载很小。
  - [sar 找出系统瓶颈的利器](https://linuxtools-rst.readthedocs.io/zh_CN/latest/tool/sar.html)
  - [10 Useful Sar (Sysstat) Examples for UNIX / Linux Performance Monitoring](https://www.thegeekstuff.com/2011/03/sar-examples/)
  - [20 sar command examples in Linux [Cheat Sheet]](https://www.golinuxcloud.com/sar-command-in-linux/)
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
- TCP常见故障排查
  - https://ms2008.github.io/2018/06/01/tcp-troubleshooting/
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

 手册
  - [Linux命令大全(手册)](https://www.linuxcool.com/)
  - [Linux Tools Quick Tutorial](https://linuxtools-rst.readthedocs.io/)
  - [100+ Linux commands cheat sheet & examples](https://www.golinuxcloud.com/linux-commands-cheat-sheet/)
  - [每天一个linux命令目录](https://www.cnblogs.com/peida/archive/2012/12/05/2803591.html)
- 性能优化
  - [Linux Performance](https://www.brendangregg.com/linuxperf.html)
  - [性能之巅：Linux 网络性能分析工具](https://www.infoq.cn/article/linux-networking-performance-analytics/)
  - [性能不好怎么办？对着清单撸一遍](https://mp.weixin.qq.com/s?__biz=MzAwNjY4NTQ4MA==&mid=2651174290&idx=1&sn=288518f030801f4d90878e806546487c&scene=1&srcid=0721NBPW2U9bCAlMyD6IR9uY&from=singlemessage&isappinstalled=0#wechat_redirect)
    - [中文翻译：用十条命令在一分钟内检查Linux服务器性能](http://www.infoq.com/cn/news/2015/12/linux-performance/)
