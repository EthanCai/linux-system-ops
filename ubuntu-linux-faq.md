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
