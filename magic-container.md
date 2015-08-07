# Docker介绍

[Docker Wikipedia](https://en.wiki2.org/wiki/Docker_(software)

Docker is an open-source project that automates the deployment of applications inside software containers, by providing an additional layer of abstraction and automation of operating-system-level virtualization on Linux. Docker uses resource isolation features of the Linux kernel such as cgroups and kernel namespaces to allow independent "containers" to run within a single Linux instance, avoiding the overhead of starting and maintaining virtual machines.

The Linux kernel's support for namespaces mostly isolates an application's view of the operating environment, including process trees, network, user IDs and mounted file systems, while the kernel's cgroups provide resource isolation, including the CPU, memory, block I/O and network. Since version 0.9, Docker includes the libcontainer library as its own way to directly use virtualization facilities provided by the Linux kernel, in addition to using abstracted virtualization interfaces via libvirt, LXC (Linux Containers) and systemd-nspawn.

According to industry analyst firm 451 Research, "Docker is a tool that can package an application and its dependencies in a virtual container that can run on any Linux server. This helps enable flexibility and portability on where the application can run, whether on premise [sic], public cloud, private cloud, bare metal, etc."

## How is this different from virtual machines?

Each virtual machine includes the application, the necessary binaries and libraries and an entire guest operating system - all of which may be tens of GBs in size.

Containers include the application and all of its dependencies, but share the kernel with other containers. They run as an isolated process in userspace on the host operating system. They’re also not tied to any specific infrastructure – Docker containers run on any computer, on any infrastructure and in any cloud.

![](./img/2015/07/container-vs-vm.jpg)

## Docker's Architecture

参考：[https://docs.docker.com/introduction/understanding-docker/](https://docs.docker.com/introduction/understanding-docker/)

Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers. Both the Docker client and the daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon. The Docker client and daemon communicate via sockets or through a RESTful API.

![](./img/2015/07/architecture.svg)

# Docs & Books

- [Get Started with Docker for Linux](http://docs.docker.com/linux/started/)
- [Get Started with Docker for Mac OS X](http://docs.docker.com/mac/started/): 需要安装boot2docker，boot2docker会安装VirtualBox、Docker、Boot2Docker management tool
- [Get Started with Docker for Windows](http://docs.docker.com/windows/started/): 需要安装boot2docker，boot2docker会安装VirtualBox、Docker、Boot2Docker management tool
- [Docker Docs](https://docs.docker.com/)
- [The Docker Book](http://book.douban.com/subject/26285268/)
- [Docker Up and Running](http://www.amazon.com/Docker-Up-Running-Karl-Matthias/dp/1491917571/ref=sr_1_1?ie=UTF8&qid=1437978051&sr=8-1&keywords=docker)

# Resources

- [Docker Hub](https://hub.docker.com/)
- [Docker Pool](http://www.dockerpool.com/)
- [DockOne](http://dockone.io/)
- [DaoCloud技术Blog](http://blog.daocloud.io/)
- [灵雀云Blog](http://www.alauda.cn/blog/)
- [UnitedStack技术分享](https://www.ustack.com/skill-share/)

# Projects

## Container

- [Docker Engine](https://www.docker.com/): An open platform for distributed applications for developers and sysadmins
	- [docker kitematic](https://kitematic.com/): Kitematic is the fastest and easiest way to start using Docker on your laptop. A completely automated process installs and configures the Docker environment on your machine in just minutes. Build and run containers through a simple, yet powerful graphical user interface (GUI).
	- [docker registry](https://www.docker.com/docker-registry): [源代码](https://github.com/docker/distribution), Docker Registry is an open source application dedicated to the storage and distribution of your Docker images. Its seamless architecture allows both for fine grain integration with other systems and high-level scalability. Aggressively developed, its vibrant community includes industry leaders and users using it at the core of their images distribution solutions.
	- [docker machine](https://www.docker.com/docker-machine): To get started with Docker, first you need to setup a Docker Engine. Docker Machine automatically sets up Docker on your computer, on cloud providers, and inside your data center. Docker Machine provisions the hosts, installs Docker Engine on them, and then configures the Docker client to talk to the Docker Engines.
	- [docker compose](https://www.docker.com/docker-compose): Distributed applications consist of many small applications that work together. Docker transforms these applications into individual containers that are linked together. Instead of having to build, run and manage each individual container, Docker Compose allows you to define your multi-container application with all of its dependencies in a single file, then spin your application up in a single command. Your application’s structure and configuration are held in a single place, which makes spinning up applications simple and repeatable everywhere.
	- [docker swarm](https://www.docker.com/docker-swarm): The nature of distributed applications requires compute resources that are also distributed. Docker Swarm provides native clustering capabilities to turn a group of Docker engines into a single, virtual Docker Engine. With these pooled resources, you can scale out your application as if it were running on a single, huge computer.

## Docker Host OS

- [CoreOS](https://coreos.com/): CoreOS produces, maintains and utilizes open source software for Linux containers and distributed systems. Projects are designed to be composable and complement each other in order to run container-ready infrastructure.
- [boot2docker](http://boot2docker.io/): boot2docker is a lightweight Linux distribution based on Tiny Core Linux made specifically to run Docker containers. It runs completely from RAM, weighs ~27MB and boots in ~5s (YMMV).
- [Atomic](http://www.projectatomic.io/): Atomic是Red Hat公司发起的以应用为中心的操作系统，它可以更方便地部署和管理你的Docker容器。Atomic基于成熟的底层操作系统，保证容器运行环境的安全，并且集成了Kubernetes、Systemd等管理工具，提供容器应用部署的全套解决方案。与传统操作系统不同，Atomic经过裁剪后体积更小更容易维护，并且集成了SELinux安全技术，让Docker容器有更好的安全隔离，还有Gockpit等工具让容器的部署和管理更加方便。
- [Ubuntu Core](http://ubuntu.com.cn/cloud/tools/snappy): Ubuntu Core is a new rendition of Ubuntu for the cloud with transactional updates. Ubuntu Core is a minimal server image with the same libraries as today’s Ubuntu, but applications are provided through a simpler mechanism. The snappy approach is faster, more reliable, and lets us provide stronger security guarantees for apps and users — that’s why we call them “snappy” applications.

## Container Management

- [kubernetes](http://kubernetes.io/): Manage a cluster of Linux containers as a single system to accelerate Dev and simplify Ops.

## Image Build

- [dockramp](https://github.com/jlhawn/dockramp): Docker 1.8.0 will introduce a new API endpoint for copying files and directories into a container. With this addition, anyone can now implement their own build system using the Docker Remote API. Dockramp is the first proof of concept for an alternative to docker build.
- [packer](https://packer.io/): Packer is a tool for creating machine and container images for multiple platforms from a single source configuration.

## Developer Tools

- [Vagrant](https://www.vagrantup.com/): Vagrant 是一个基于 Ruby 的工具，用于创建和部署虚拟化开发环境。它使用 Oracle 的开源 VirtualBox 虚拟化系统，使用 Chef 创建自动化虚拟环境。 
- [Panamax](http://panamax.io/): Panamax是一个CenturyLink开源的Docker管理工具，用户可以把多个Docker容器组合为模板并分享到GitHub。Panamax中的应用是由基于Docker镜像的独立服务组合而成，这些Docker镜像来自Docker Hub或者其它的Docker registry。Web的用户界面允许每个服务可以连接到其他服务，并可以配置环境变量、端口绑定、卷。另外也可以添加自定义的Docker运行命令。当这些服务组合在一起成为一个具备完整功能的应用后就可以作为一个模板保存到GitHub。Panamax的最初版本运行在由Vagrant管理的VirtualBox上，由于Vagrant的限制，目前Panamax仅可运行在Mac和Linux的VirtualBox上，并不支持其他虚拟化平台。CenturyLink的云平台也将会支持Panamax。

## Virtual Machine Host

- [Xen](http://www.xenproject.org/): Xen 是一个开放源代码虚拟机监视器，由剑桥大学开发。它打算在单个计算机上运行多达100个满特征的操作系统。操作系统必须进行显式地修改（“移植”）以在Xen上运行（但是提供对用户应用的兼容性）。这使得Xen无需特殊硬件支持，就能达到高性能的虚拟化。
- [XenServer](http://xenserver.org/): XenServer is the leading open source virtualization platform, powered by the Xen Project hypervisor and the XAPI toolstack. It is used in the world's largest clouds and enterprises.
- [Kernel Virtual Machine](http://www.linux-kvm.org/page/Main_Page): KVM (for Kernel-based Virtual Machine) is a full virtualization solution for Linux on x86 hardware containing virtualization extensions (Intel VT or AMD-V). It consists of a loadable kernel module, kvm.ko, that provides the core virtualization infrastructure and a processor specific module, kvm-intel.ko or kvm-amd.ko.
- [Hyper](https://hyper.sh/): Hyper 是一种 App-Centric 的虚拟化技术，我们完全摒弃了传统虚机上必须和物理机一样，运行一个完整 OS 这种看似显然的假设，我们让Docker Image 直接运行在 Hypervisor 上。我们让一组容器直接启动在 hypervisor 上的时间达到 350 毫秒，并且还在进一步优化。而且所有这些，都是“开箱即得的”。当然有人会问，有了容器为什么还要虚机。诚然，虚机并不是所有人都需要的，但是，虚机天然具备更好的隔离性；虚拟机也仍然存在于很多企业应用的协议栈中，这样一个依赖更少、开箱即得，而且还带有 Pod、persist mode 等附加丰富特性的应用，是不少场景中都需要的。而我们最期待的，就是去引爆新的容器服务 —— CaaS。.传统虚拟机的问题其实在于过于刻意模仿物理机，刻意要承载完整操作系统，启动一台虚拟机要若干秒，甚至几分钟，Image 有若干GB，加载传播都很慢，但其实根本没有这个必要，Hyper希望兼取两者的强项
- [OpenVZ](http://openvz.org/Main_Page): OpenVZ is container-based virtualization for Linux. OpenVZ creates multiple secure, isolated Linux containers (otherwise known as VEs or VPSs) on a single physical server enabling better server utilization and ensuring that applications do not conflict. Each container performs and executes exactly like a stand-alone server; a container can be rebooted independently and have root access, users, IP addresses, memory, processes, files, applications, system libraries and configuration files. 

## Virtual Machine OS

- [Clear Linux](https://clearlinux.org/): The Clear Linux* Project for Intel® Architecture is a project that is building a Linux OS distribution for various cloud use cases. The goal of Clear Linux OS is to showcase the best of Intel Architecture technology, from low-level kernel features to more complex items that span across the entire operating system stack.

## PaaS

- [Flynn](https://flynn.io/): Flynn是一个使用Go语言编写的开源PaaS平台，Flynn使用模块化的设计，任何一个模块都可以独立的进行修改、升级和替换。Flynn的目标是简化分布式环境中应用的部署和维护，通过使用git push命令，Flynn就可以将应用部署到Docker，从而省去了复杂的配置和操作。Flynn的架构大致分为两层，Layer 0是底层的资源层，提供分布式配置、任务调度、服务发现、主机隔离等基础功能；Layer 1基于Layer 0构建了一个用于集群中管理、部署、扩展服务的系统，主要包括管理API/客户端、Git接收器、数据存储、路由。Flynn目前仍在开发中，尚未发布稳定版，但已经获得了很多公司的资助，它被称为是下一代的开源PaaS平台。
- [Deis](http://deis.io/): Deis也是一个支持共有云和私有云的开源PaaS系统，Deis基于Docker和CentOS构建了一个类Heroku的PaaS系统。Deis主要设计用来和不同的云提供商进行交互，目前支持 Rackspace、EC2、 DigitalOcean、Google Compute Engine、Bare-Metal。Deis使用out-of-the-box的方式支持Ruby、Python、Node.js、Java、Clojure、Scala、Play、PHP、Perl、Dart和Go语言，同样支持git push部署。Flynn和Deis都是两个基于Docker的云计算微PaaS技术，关于它们的区别，可以参考这篇文章，作者从架构、实现方式等多方面对二者进行了比较，Deis目前也尚未发布1.0版本，但在GitHub上已经有2000+的star量。
- [Dokku](https://github.com/progrium/dokku): Dokku是一个迷你版的Heroku，基于Docker使用100行左右的Bash代码编写，简单的安装和配置后，即可使用Git命令将应用部署到本地的Dokku平台（当使用git push命令的时候，Dokku会使用buildpack检测应用，然后再部署）。Dokku实际上相当于一个单机版的Heroku，它包含4个组件，分别是Docker、Buildstep、pluginhook、sshcommand。Dokku目前支持Node.js、Ruby、Python。

## IaaS

- [OpenStack](http://www.openstack.org/): Open source software for creating private and public clouds.

## CI

- [Drone](https://github.com/drone/drone): Drone是一个使用Go语言编写的基于Docker的持续集成系统。Drone可以快速提供隔离的虚拟环境编译测试，而且根据需要保留结果，比使用VM更加简洁有效。如何使用 Drone和Docker搭建全功能的CI服务器可以参考此文。使用Drone搭建CI服务器后，代码可以不离开公司网络即可测试，这非常适合大公司的保密原则，另外，由于Drone基于Docker使用，所以部署到生产环境也非常容易。

# Articles

演讲:

- 2015-06-16: [基于Docker容器的云计算平台搭建实战](http://www.infoq.com/cn/presentations/build-cloud-computing-platform-based-on-docker-container)

深入浅出Docker系列:

- 2014-07-31: [深入浅出Docker（一）：Docker核心技术预览](http://www.infoq.com/cn/articles/docker-core-technology-preview)
- 2014-08-15: [深入浅出Docker（二）：Docker命令行探秘](http://www.infoq.com/cn/articles/docker-command-line-quest)
- 2014-08-29: [深入浅出Docker（三）：Docker开源之路](http://www.infoq.com/cn/articles/docker-open-source-road)
- 2014-09-12: [深入浅出Docker（四）：Docker的集成测试部署之道](http://www.infoq.com/cn/articles/docker-integrated-test-and-deployment)
- 2014-10-23: [深入浅出Docker（五）：基于Fig搭建开发环境](http://www.infoq.com/cn/articles/docker-build-development-environment-based-on-fig)
- 2015-03-13: [深入浅出Docker（六）：像谷歌一样部署你的应用](http://www.infoq.com/cn/articles/deploy-your-application-like-google)

DockerOne技术分享:

- [DockOne技术分享（一）：Dockerfile与Docker构建流程解读](http://dockone.io/article/346)
- [DockOne技术分享（二）：集群规模下日志处理和网络方案](http://dockone.io/article/355)
- [DockOne技术分享（四）：AppC和Docker的对比](http://dockone.io/article/383)
- [DockOne技术分享（十四）：腾讯蓝鲸数据平台之告警系统](http://dockone.io/article/537)

Docker背后的内核知识:

- 2015-03-12: [Docker背后的内核知识——Namespace资源隔离](http://www.infoq.com/cn/articles/docker-kernel-knowledge-namespace-resource-isolation)
- 2015-04-20: [Docker背后的内核知识——cgroups资源限制](http://www.infoq.com/cn/articles/docker-kernel-knowledge-cgroups-resource-isolation)

Docker源码分析:

[Docker源码分析](http://www.infoq.com/cn/search.action?queryString=Docker%E6%BA%90%E7%A0%81%E5%88%86%E6%9E%90&page=1&searchOrder=&sst=6mw0v60aY59HlPFE)

Kubernetes文章:

- 论文: [Large-scale cluster management at Google with Borg](https://research.google.com/pubs/pub43438.html)，[备份](./Large-scale cluster management at Google with Borg.pdf)
	- [Google发布论文 披露大规模集群管理工具Borg的细节](http://www.infoq.com/cn/news/2015/04/google-borg)
	- [Docker背后的容器集群管理——从Borg到Kubernetes（一）](http://www.infoq.com/cn/articles/docker-container-cluster-management-part-01/)
- 2014-10-30: [Kubernetes系统架构简介](http://www.infoq.com/cn/articles/Kubernetes-system-architecture-introduction)
- 2014-10-30: [Kubernetes初探](http://blog.csdn.net/zhangjun2915/article/details/40598151)
- 2014-12-03: [CentOS 7实战Kubernetes部署](http://www.infoq.com/cn/articles/centos7-practical-kubernetes-deployment)
- 2015-01-09: [An introduction to containers, Kubernetes, and the trajectory of modern cloud computing](http://googlecloudplatform.blogspot.jp/2015/01/in-coming-weeks-we-will-be-publishing.html)
- 2015-01-22: [What makes a container cluster?](http://googlecloudplatform.blogspot.pt/2015/01/what-makes-a-container-cluster.html)

其它文章:

- 2014-08-19: [十大基于Docker的开发工具](http://www.infoq.com/cn/news/2014/08/top-10-open-source-docker)
- 2014-09-19: [Docker 资源管理](http://segmentfault.com/a/1190000000681188)
- 2014-11-26: [Docker at Shopify: How we built containers that power over 100,000 online shops](http://www.shopify.com/technology/15934308-docker-at-shopify-how-we-built-containers-that-power-over-100-000-online-shops), [中文版](http://www.csdn.net/article/2014-11-25/2822806)
- 2015-02-13: [唱衰Docker，给大红大火的Docker泼点冷水](http://www.infoq.com/cn/articles/bad-mouthing-docker)
- 2015-05-19: [Eric Brewer：容器和微服务是计算的未来](https://linux.cn/article-5464-1.html)
- 2015-06-02: [Docker背后的容器管理——Libcontainer深度解析](http://www.infoq.com/cn/articles/docker-container-management-libcontainer-depth-analysis)

# FAQ

## Docker client communicating with remote docker host

参考[Docker client communicating with docker host](http://stackoverflow.com/questions/26481258/docker-client-communicating-with-docker-host)

Using the -H tcp://127.0.0.1:5555 docker daemon option on the UbuntuA machine will instruct docker to bind to the loopback network interface (127.0.0.1). As a result it will only accept connections originating from the UbuntuA machine.

If you want to accept connections incoming from any network interface use -H tcp://0.0.0.0:5555. Be aware that anyone that would be able to connect to your UbuntuA machine on port 5555 will be able to control your docker host. You need to protect it with firewall rules to allow only UbuntuB to connect to UbuntuA on port 5555.

