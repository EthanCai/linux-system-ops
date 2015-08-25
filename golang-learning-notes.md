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

社区：

- [golang中国](http://golangtc.com/)
- [go友团](http://golanghome.com/)

工具：

- [Go语言在线交互教程](http://tour.golang.org/welcome/1)
- [Package sources](http://golang.org/src/)
- [Package documentation](http://golang.org/pkg/)
- [Command documentation](http://golang.org/doc/cmd)
- [Language specification](http://golang.org/ref/spec)
- [Memory Module](http://golang.org/ref/mem)
- [effective go - go programming style guide](http://golang.org/doc/effective_go.html)

# Projects

- [Beego](http://beego.me/): 一个使用 Go 的思维来帮助您构建并开发 Go 应用程序的开源框架

# Tools


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

