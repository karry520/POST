---
title: Linux-简介
date: 2018-01-24 21:21:36
tags: Linux
---

![Linux-category](/image/Linux-category.jpeg)

- ### Redhat系列

---
目前许多高手都使用它，长相一般但却很强悍，一般是Linux高手的首选系统，相比之下就是桌面系统有点不大一样，拥有强大的rpm软件包管理系统，界面更加简洁，如果你不喜欢太多花哨的桌面系统可以考虑用它！ Redhat系列，包括RHEL(Redhat Enterprise Linux，也就是所谓的RedhatAdvance Server，收费版本)、FedoraCore(由原来的Redhat桌面版本发展而来，免费版本)、CentOS(RHEL的社区克隆版本，免费)。Redhat应该说是在国内使用人群最多的Linux版本，甚至有人将Redhat等同于Linux，而有些老鸟更是只用这一个版本的Linux。所以这个版本的特点就是使用人群数量大，资料非常多，言下之意就是如果你有什么不明白的地方，很容易找到人来问，而且网上的一般Linux教程都是以Redhat为例来讲解的。Redhat系列的包管理方式采用的是基于RPM包的YUM包管理方式，包分发方式是编译好的二进制文件。稳定性方面RHEL和CentOS的稳定性非常好，适合于服务器使用，但是Fedora Core的稳定性较差，最好只用于桌面应用。
- ### Debian系列

---
an系列，包括Debian和Ubuntu等。Debian是社区类Linux的典范，是迄今为止最遵循GNU规范的Linux系统。Debian最早由Ian Murdock于1993年创建，分为三个版本分支（branch）： stable, testing 和 unstable。其中，unstable为最新的测试版本，其中包括最新的软件包，但是也有相对较多的bug，适合桌面用户。testing的版本都经过unstable中的测试，相对较为稳定，也支持了不少新技术（比如SMP等）。而stable一般只用于服务器，上面的软件包大部分都比较过时，但是稳定和安全性都非常的高。Debian最具特色的是apt-get / dpkg包管理方式，其实Redhat的YUM也是在模仿Debian的APT方式，但在二进制文件发行方式中，APT应该是最好的了。Debian的资料也很丰富，有很多支持的社区，有问题求教也有地方可去。
- ### Gentoo

---
Gentoo，伟大的Gentoo是Linux世界最年轻的发行版本，正因为年轻，所以能吸取在她之前的所有发行版本的优点，这也是Gentoo被称为最完美的Linux发行版本的原因之一。Gentoo最初由Daniel Robbins（FreeBSD的开发者之一）创建，首个稳定版本发布于2002年。由于开发者对FreeBSD的熟识，所以Gentoo拥有媲美FreeBSD的广受美誉的ports系统——Portage包管理系统。不同于APT和YUM等二进制文件分发的包管理系统，Portage是基于源代码分发的，必须编译后才能运行，对于大型软件而言比较慢，不过正因为所有软件都是在本地机器编译的，在经过各种定制的编译参数优化后，能将机器的硬件性能发挥到极致。Gentoo是所有Linux发行版本里安装最复杂的，但是又是安装完成后最便于管理的版本，也是在相同硬件环境下运行最快的版本。
- ### FreeBSD

---
需要强调的是：FreeBSD并不是一个Linux系统！但FreeBSD与Linux的用户群有相当一部分是重合的，二者支持的硬件环境也比较一致，所采用的软件也比较类似，所以可以将FreeBSD视为一个Linux版本来比较。FreeBSD拥有两个分支：stable和current。顾名思义，stable是稳定版，而 current则是添加了新技术的测试版。FreeBSD采用Ports包管理系统，与Gentoo类似，基于源代码分发，必须在本地机器编后后才能运行，但是Ports系统没有Portage系统使用简便，使用起来稍微复杂一些。FreeBSD的最大特点就是稳定和高效，是作为服务器操作系统的最佳选择，但对硬件的支持没有Linux完备，所以并不适合作为桌面系统。
- ### OpenSUSE

---
 OpenSUSE：在欧洲非常流行的一个Linux，由Novell公司发放，号称是世界上最华丽的操作系统，独家开发的软件管理程序zypper|| yast得到了许多用户的赞美，和ubuntu一样，支持kde和gnome，xface等桌面，桌面特效比较丰富，缺点是KDE虽然华丽多彩，但比较不 稳定。新手用这个也很容易上手。
