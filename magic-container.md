# Docker介绍

[Docker Wikipedia](https://en.wiki2.org/wiki/Docker_(software))

Docker is an open-source project that automates the deployment of applications inside software containers, by providing an additional layer of abstraction and automation of operating-system-level virtualization on Linux. Docker uses resource isolation features of the Linux kernel such as cgroups and kernel namespaces to allow independent "containers" to run within a single Linux instance, avoiding the overhead of starting and maintaining virtual machines.

The Linux kernel's support for namespaces mostly isolates an application's view of the operating environment, including process trees, network, user IDs and mounted file systems, while the kernel's cgroups provide resource isolation, including the CPU, memory, block I/O and network. Since version 0.9, Docker includes the libcontainer library as its own way to directly use virtualization facilities provided by the Linux kernel, in addition to using abstracted virtualization interfaces via libvirt, LXC (Linux Containers) and systemd-nspawn.

According to industry analyst firm 451 Research, "Docker is a tool that can package an application and its dependencies in a virtual container that can run on any Linux server. This helps enable flexibility and portability on where the application can run, whether on premise [sic], public cloud, private cloud, bare metal, etc."

# Docs & Books

- [Docker Docs](https://docs.docker.com/)
- [The Docker Book](http://book.douban.com/subject/26285268/)
- [Docker Up and Running](http://www.amazon.com/Docker-Up-Running-Karl-Matthias/dp/1491917571/ref=sr_1_1?ie=UTF8&qid=1437978051&sr=8-1&keywords=docker)
- [Docker —— 从入门到实践](https://www.gitbook.com/book/yeasy/docker_practice/details)

# Resources

- [Docker Hub](https://hub.docker.com/)
- [Docker Pool](http://www.dockerpool.com/)
- [DockOne](http://dockone.io/)
- [DaoCloud](https://www.daocloud.io/)
- [灵雀云](http://www.alauda.cn/)

# Projects

## Container

- [Docker](https://www.docker.com/): An open platform for distributed applications for developers and sysadmins

## OS

- [CoreOS](https://coreos.com/): CoreOS produces, maintains and utilizes open source software for Linux containers and distributed systems. Projects are designed to be composable and complement each other in order to run container-ready infrastructure.
- [Clear Linux](https://clearlinux.org/): The Clear Linux* Project for Intel® Architecture is a project that is building a Linux OS distribution for various cloud use cases. The goal of Clear Linux OS is to showcase the best of Intel Architecture technology, from low-level kernel features to more complex items that span across the entire operating system stack.
- [boot2docker](http://boot2docker.io/): boot2docker is a lightweight Linux distribution based on Tiny Core Linux made specifically to run Docker containers. It runs completely from RAM, weighs ~27MB and boots in ~5s (YMMV).

## Container Management

- [kubernetes](http://kubernetes.io/): Manage a cluster of Linux containers as a single system to accelerate Dev and simplify Ops.
- [Apache Mesos](http://mesos.apache.org/): Apache Mesos abstracts CPU, memory, storage, and other compute resources away from machines (physical or virtual), enabling fault-tolerant and elastic distributed systems to easily be built and run effectively.
- [kitematic](https://kitematic.com/): The easiest way to start using Docker on Mac & Windows

## Virtual Machine

- [Xen](http://www.xenproject.org/): Xen 是一个开放源代码虚拟机监视器，由剑桥大学开发。它打算在单个计算机上运行多达100个满特征的操作系统。操作系统必须进行显式地修改（“移植”）以在Xen上运行（但是提供对用户应用的兼容性）。这使得Xen无需特殊硬件支持，就能达到高性能的虚拟化。
- [XenServer](http://xenserver.org/): XenServer is the leading open source virtualization platform, powered by the Xen Project hypervisor and the XAPI toolstack. It is used in the world's largest clouds and enterprises.
- [Kernel Virtual Machine](http://www.linux-kvm.org/page/Main_Page): KVM (for Kernel-based Virtual Machine) is a full virtualization solution for Linux on x86 hardware containing virtualization extensions (Intel VT or AMD-V). It consists of a loadable kernel module, kvm.ko, that provides the core virtualization infrastructure and a processor specific module, kvm-intel.ko or kvm-amd.ko.
- [Hyper](https://hyper.sh/): Hyper 是一种 App-Centric 的虚拟化技术，我们完全摒弃了传统虚机上必须和物理机一样，运行一个完整 OS 这种看似显然的假设，我们让Docker Image 直接运行在 Hypervisor 上。我们让一组容器直接启动在 hypervisor 上的时间达到 350 毫秒，并且还在进一步优化。而且所有这些，都是“开箱即得的”。当然有人会问，有了容器为什么还要虚机。诚然，虚机并不是所有人都需要的，但是，虚机天然具备更好的隔离性；虚拟机也仍然存在于很多企业应用的协议栈中，这样一个依赖更少、开箱即得，而且还带有 Pod、persist mode 等附加丰富特性的应用，是不少场景中都需要的。而我们最期待的，就是去引爆新的容器服务 —— CaaS。.传统虚拟机的问题其实在于过于刻意模仿物理机，刻意要承载完整操作系统，启动一台虚拟机要若干秒，甚至几分钟，Image 有若干GB，加载传播都很慢，但其实根本没有这个必要，Hyper希望兼取两者的强项

## IaaS

- [OpenStack](http://www.openstack.org/): Open source software for creating private and public clouds.

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

其它文章:

- 2014-09-19: [Docker 资源管理](http://segmentfault.com/a/1190000000681188)
- 2014-10-30: [Kubernetes系统架构简介](http://www.infoq.com/cn/articles/Kubernetes-system-architecture-introduction)
- 2014-11-26: [Docker at Shopify: How we built containers that power over 100,000 online shops](http://www.shopify.com/technology/15934308-docker-at-shopify-how-we-built-containers-that-power-over-100-000-online-shops), [中文版](http://www.csdn.net/article/2014-11-25/2822806)
- 2015-05-19: [Eric Brewer：容器和微服务是计算的未来](https://linux.cn/article-5464-1.html)


