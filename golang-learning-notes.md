# Books

参考：[Gobooks](https://github.com/dariubs/GoBooks)

- [Go语言编程](http://book.douban.com/subject/11577300/)
- [An Introduction to Programming in Go 2012.9.3](http://www.amazon.com/Introduction-Programming-Go-Caleb-Doxsey/dp/1478355824/ref=sr_1_2?ie=UTF8&qid=1438760964&sr=8-2&keywords=golang): 简短的介绍Go语言的书籍，但未覆盖很多深入的内容。
- [Go Programming Blueprints 2015](http://www.amazon.com/Go-Programming-Blueprints-Development-Challenges/dp/1783988029/ref=sr_1_1?ie=UTF8&qid=1438760964&sr=8-1&keywords=golang): Amazon评价很高，这本书介绍了很多高级主题
- Network programming with Go.(2012)
- [Programming in Go 2012.5.14](http://www.amazon.com/Programming-Go-Creating-Applications-Developers/dp/0321774639/ref=sr_1_4?ie=UTF8&qid=1438760964&sr=8-4&keywords=golang): 这本书的三个优点：High quality code samples；Idiomatic Go code；Details that aren't in the docs
- Ready to Go
- The Go Programming Language Phrasebook.(2012)
- [The Way to Go a Thorough Introduction to the Go Programming Language 2012.3.8](http://www.amazon.com/Way-Go-Thorough-Introduction-Programming/dp/1469769166/ref=sr_1_9?ie=UTF8&qid=1438760964&sr=8-9&keywords=golang)
- [build-web-application-with-golang](https://github.com/astaxie/build-web-application-with-golang) 

# Resources

资源：

- [golang](http://golang.org/)
- [golang国内镜像](http://docscn.studygolang.com/)
- [golang资料集](https://github.com/ty4z2008/Qix/blob/master/golang.md)
- [Go Packages](https://godoc.org/)
- [Go语言资料收集](https://github.com/wonderfo/wonderfogo/wiki)

社区：

- [golang中国](http://golangtc.com/)
- [go友团](http://golanghome.com/)
- [Go邮件组](http://groups.google.com/group/golang-nuts)
- [Go的中文邮件组](http://groups.google.com/group/golang-china)

工具：

- [Go-search](http://go-search.org/): 查找Go packages
- [Go语言在线交互教程，及在线运行IDE](http://tour.golang.org/welcome/1)
- [Go by Example](https://gobyexample.com/): Go by Example is a hands-on introduction to Go using annotated example programs. 

# 学习路径

1. 安装Go
	- 参考[Get Started](http://golang.org/doc/install)安装Golang runtime，如果OS X通过Homebrew安装
	- IDE
		- 使用Sublime，需要[安装GoSublime Package](https://github.com/DisposaBoy/GoSublime)
		- 使用Atom，需要安装[Go-Plus Package](https://atom.io/packages/go-plus)
		- 使用IDEA，需要安装[go-lang-idea-plugin](https://github.com/go-lang-plugin-org/go-lang-idea-plugin/wiki/Documentation), 文档见[这里](https://github.com/go-lang-plugin-org/go-lang-idea-plugin/wiki/Documentation)
1. 练习搭建基本的Workspace，并熟悉Workspace的结构、Go代码结构、编写基本的单元测试、`Go fmt/build/install/run/test`等命名的使用
	- [How to Write Go Code](http://golang.org/doc/code.html)
	- [Go命令文档](http://golang.org/doc/cmd)
1. 编写Golang程序
	- [Effective Go - Go语言编码规范](http://golang.org/doc/effective_go.html)
	- [Go语言Package文档](http://golang.org/pkg/)
1. 其它
	- [Golang Memory Module](http://golang.org/ref/mem)
	- [Go语言源代码](https://go.googlesource.com/go/)：在线查看Go语言源代码访问[这里](http://golang.org/src/)
	- [Go语言语法规格](http://golang.org/ref/spec)
	
# Projects

# Dev Tools

- [GoPM](https://github.com/gpmgo/gopm): Go Package Manager (gopm) is a package manager and build tool for Go.
- [godep](https://github.com/tools/godep): dependency tool for go
- [gb](https://github.com/constabulary/gb): the project based build tool for Go
- [Delve](https://github.com/derekparker/delve/): Delve is a debugger for the Go programming language.
- [Go plugin for IntelliJ](https://github.com/go-lang-plugin-org/go-lang-idea-plugin): Google Go language IDE built using the IntelliJ Platform
- [Wide](https://github.com/b3log/wide): A Web-based IDE for Teams using Go programming language/Golang

## Framework

- [Beego](http://beego.me/): 一个使用 Go 的思维来帮助您构建并开发 Go 应用程序的开源框架
- [revel](http://revel.github.io/): A high-productivity web framework for the Go language.
- [tango](https://github.com/lunny/tango): Micro & pluggable web framework for Go
- [Gobot](http://gobot.io/): Gobot is a framework for robotics, physical computing, and the Internet of Things, written in the Go programming language.
- [GRPC](http://www.grpc.io/): A high performance, open source, general RPC framework that puts mobile and HTTP/2 first.
- [bosun](https://github.com/bosun-monitor/bosun): Time Series Alerting Framework
- [gokit](https://github.com/go-kit/kit): Go kit is a distributed programming toolkit for building microservices in large organizations. We solve common problems in distributed systems, so you can focus on your business logic.

## SDK & Library

- [bleve](https://github.com/blevesearch/bleve): A modern text indexing library for go
- [weixinmp](https://github.com/sidbusy/weixinmp): 微信公众平台SDK for Go
- [Gorilla web toolkit](http://www.gorillatoolkit.org/): Gorilla is a web toolkit for the Go programming language.
- [xorm](https://github.com/go-xorm/xorm): Simple and Powerful ORM for Go, support mysql/sqlite3/postgres/mssql/oracle/tidb/ql
- [GoRazor](https://github.com/sipin/gorazor): Razor view engine for Golang

## Business Application

- [captcha](https://github.com/jianxinio/captcha): Golang实现的验证码服务 
- [Gor](https://github.com/wendal/gor): Golang编写的静态博客引擎
- [heim](https://github.com/euphoria-io/heim): A real-time community platform
- [Mattermost](https://github.com/mattermost/platform): Mattermost is an open-source team communication service. It brings team messaging and file sharing into one place, accessible across PCs and phones, with archiving and search.
- [ohlala](https://github.com/QLeelulu/ohlala): 觅链，一个具有社会化媒体属性的链接分享与评论平台。类似Reddit
- [Pachyderm](https://github.com/pachyderm/pachyderm): Containerized Data Analytics
- [Pholcus](https://github.com/henrylee2cn/pholcus): Pholcus（幽灵蛛）是一款纯Go语言编写的高并发、分布式、重量级爬虫软件，支持单机、服务端、客户端三种运行模式，拥有Web、GUI、命令行三种操作界面；规则简单灵活、批量任务并发、输出方式丰富（mysql/mongodb/csv/excel等）、有大量Demo共享；同时她还支持横纵向两种抓取模式，支持模拟登录和任务暂停、取消等一系列高级功能 
- [uniqush-push](https://github.com/uniqush/uniqush-push): Uniqush is a free and open source software which provides a unified push service for server-side notification to apps on mobile devices.
 
## Infrastructure Application

- [dkron](https://github.com/victorcoder/dkron): Distributed, fault tolerant job scheduling system
- [GoTTY](https://github.com/yudai/gotty): Share your terminal as a web application
- [Open-Falcon企业级监控系统解决方案](http://open-falcon.com/): Open-Falcon 是小米运维部开源的一款互联网企业级监控系统解决方案.
- [Prometheus](https://github.com/prometheus/prometheus): Prometheus is a systems and service monitoring system. It collects metrics from configured targets at given intervals, evaluates rule expressions, displays the results, and can trigger alerts if some condition is observed to be true.
- [restic](https://github.com/restic/restic): restic backup program
- [serf](https://github.com/hashicorp/serf): Service orchestration and management tool
- [syncthing](https://github.com/syncthing/syncthing): Open Source Continuous File Synchronization
- [Tyk API Gateway](https://github.com/lonelycode/tyk): Tyk is a lightweight, open source API Gateway and enables you to control who accesses your API, when they access it and how they access it. Tyk will also record detailed analytics on how your users are interacting with your API and when things go wrong.
- [webcron](https://github.com/codeskyblue/webcron): A new crontab that have a web page in order to replace the original crontab. Now it can try on test.
- [Webhook](https://github.com/adnanh/webhook): webhook is a lightweight configurable tool written in Go, that allows you to easily create HTTP endpoints (hooks) on your server, which you can use to execute configured commands.
- [gitea - a self-hosted Git service.](https://github.com/go-gitea/gitea)
- [termui- Golang terminal dashboard](https://github.com/gizak/termui)
- [NSQ](http://nsq.io/): A realtime distributed messaging platform

# Tools

- [toxy](https://github.com/h2non/toxy): Hackable HTTP proxy to simulate server failure scenarios and unexpected network conditions

# FAQ

## What is difference between Goroutines vs OS threads?

参考：

- [What-is-difference-between-Goroutines-vs-OS-threads](http://www.quora.com/What-is-difference-between-Goroutines-vs-OS-threads)
- [goroutine背后的系统知识](http://www.infoq.com/cn/articles/knowledge-behind-goroutine)
- [golang的goroutine是如何实现的?](http://www.zhihu.com/question/20862617)
- [Concurrency, Goroutines and GOMAXPROCS](http://www.goinggo.net/2014/01/concurrency-goroutines-and-gomaxprocs.html)
- [Green threads](http://www.wikiwand.com/en/Green_threads)

The Go runtime multiplexes a potentially large number of goroutines onto a smaller number of OS threads, and goroutines blocked on I/O are handled efficiently using epoll or similar facilities.  Goroutines have tiny stacks that grow as needed, so it is practical to have hundreds of thousands of goroutines in your program. This allows the programmer to use concurrency to structure their program without being overly concerned with thread overhead.

## Go语言和其它语言的比较

参考：

- [我为什么从python转向go](http://www.jianshu.com/p/afa14e631930)
- [Node.js vs Golang: Battle of the Next-Gen Languages](http://www.hostingadvice.com/blog/nodejs-vs-golang/)

## Go语言主要版本和版本变更内容是哪些？

参考：

- [Release History](http://golang.org/doc/devel/release.html)



