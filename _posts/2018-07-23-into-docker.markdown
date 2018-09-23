---
layout: single
title:  "Into Docker"
categories: Cloud
comments: true
author: nadaghanem
---

Being either a developer or a DevOps engineer, you may have heard the term Virtualization, and now docker containers gain attract 
many industries. A good question to answer is, why should I decide between these two?
The basic answer is software shipping, you need to be able to move your software from machine to another easily and at a cheap cost.
If you own an industry, you probably have limited resources (servers, routers, disks, memories,..etc), however, you should be able to handle heavy client requests and loads. 
A reasonable solution is to run multiple applications on the same server, but how to guarantee that the applications will work seamlessly 
since they all share the same resources.

In Virtualization, multiple guest operating systems are built on the top of the host OS (the main operating system) using Hypervisor, such that each application runs separately on its guest OS (virtual machine). This article is an introduction of Docker containers. 
Instead of starting directly to explain what is docker, I prefer to dig a little into Virtualization as we are familiar with.
The following image showcases the structure of Virtualization. The main component is the Hypervisor, which is also called Virtual Machine 
Mentor (VMM). It allows managing several isolated virtual machines and organizes their access to physical resources. 
IBM brought Hypervisor to life in 1956 and still exists until now.

![](https://i.imgur.com/wZFwk3z.png)

## Types of Hypervisors:

- **Type 1**: has a direct link to the physical hardware (e.g. Hyperkit on mac, Hyper-V on windows , KVM on linux).
- **Type 2**: a software runs on the top of host OS (e.g. VirtualBox, VMware)

## Virtualization Flaws:

- Heavy software (requires large storage and long running time)
- Allows limited number of running virtual machines 

## Why Docker?

Docker is considered Virtualization 2.0, though it differs from the traditional Virtualization, they have both isolate applications running on the host operating system. Docker might not be a replacement for Virtualization, but it came to solve Virtualization problems and simplifying software building and deployment with minimum cost.


## What is Docker?

Analogous to goods shipping, containers are used to hold goods from place to another securely. You can ship whatever you want while making sure it will arrive anywhere. Each container holds one type of good, for example, you can't ship shoes with clothes in the same container.
In the image below, you can see the difference between Virtualization and Docker containers, Docker Engine replaces the Hypervisor in Virtualization. All containers are built on the top of the host operating system, without the need for multiple guest OS

![](https://i.imgur.com/xeMELtE.jpg)

Docker is a portable container engine used to ship software form machine to another without considering the included software, build, and dependencies.

## Docker Principles:
- Separation of concerns
- Build once, run anywhere
- Automation
- Low cost


Docker begins as a dotCloud Inc, a private company, until 2013, they announced Docker project to the public as an open source. Docker doesn't appear as an independent project, in fact, docker containers inherit the idea from [LXC- Linux Containers] (https://linuxcontainers.org/lxc/manpages/man5/lxc.container.conf.5.html). Docker extracted LXC functionalities from low-level Virtualization and implemented it into a higher level by using API, making it accessible and applicable for everyone. Docker CTO, Solomon Hyks explained briefly this in his talk
[the future of Linux container] (https://www.youtube.com/watch?v=wW9CAH9nSLs).


## Facts about Docker project:

- Docker CE (community edition) became an open source in 2013
- Written in Golang
- Fully supported by Linux, with possibility to be installed on other operating systems

## Containers vs. images

Containers is a runtime encapsulated environment of application, binaries, and dependencies.
Images are snapshots of containers They are shared by default in [Docker Hub](https://hub.docker.com/), which is a public registry of Docker images, that includes more than 240K repositories.

**In summary, here are some points to consider Docker containers:**

- Docker Containers work only on the top of one operating systems, and doesn't need guest operating systems.
- Unlike Virtual machines, Docker containers are lightweight (occupies less memory, disks,..etc).
- As a consequence from the previous advantage, you can build many containers on the top of your OS.
- Fast software shipping and running with minimum resources and low cost.

I will be writing more about Docker Installation, uses, and commands in the next articles.

**Resources**
- [Docker Documentation](https://docs.docker.com/)
- [Container for everyone](https://linuxacademy.com/templates/default/assets/pdf/containers-for-everyone-ebook.pdf)



