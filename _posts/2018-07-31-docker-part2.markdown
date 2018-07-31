---
layout: single
title:  "Docker Installation and Usage"
categories: Cloud
comments: true
---

This article aims to give you the basic skills required to build Docker containers. A general understanding about Docker might be useful to connect concepts together. If you don't know what is Docker, please review [Docker intro](http://localhost:4000/cloud/into-docker/).

Transforming to Docker is a wise decision for most companies, Docker efficiently enhances their performance and scalability at low cost.

Lets put the use of Docker into a real example: an enterprise that runs an Airline reservation system, they use many services such as scheduling, fare tariffs, passenger reservation records..etc. This system receives thousands of daily requests. They probably deploy their software across many nodes/computers on the cloud, each computer runs a service.

Suppose they have 3 services and they want to run each one on 5 nodes, which means they will ire 3*5 nodes for the entire application. This will add layers of network overhead and more cost.  Docker containers can be a good alternative. Since containers separate applications within the same machine, they may use 5 nodes with 3 containers to resolve the issue. Each container runs a copy of a single service.
Developers also take advantage of working with containers, they can easily test their application while having all services work together using [CI](https://en.wikipedia.org/wiki/Continuous_integration). 


## Table of Content

1. [Docker Components](#docker-component)
1. [Docker installation](#docker-install)
    - [Install Docker on Linux](#docker-linux)
    - [Installing Docker in Windows](#docker-windows)
1. [Docker Main Terminologies](#docker-terminologies)
1. [Docker Commands](#docker-commands)
1. [Build a Simple Docker Image](#simple-image)
 

## Docker Components:

Docker is a client-server application installed on one machine. You run the Docker Client from the terminal by using Docker commands, Docker server executes the commands, this communication is applied via API. For example, a client might send a request to create an image, the server handles the request and execute the command. The image will be saved locally, and the client has the choice to move the image online into the Docker registry.

- **Docker Client** which sends commands like running containers, remove containers, stop or start containers, build imagees, ..etc)
- **Docker Server** also called Engine or Daemon. listen to clients commands and act based on it, which aim to control containers, images, volumes,..etc.
- **Docker Registry** is a space to stores Docker images locally or remotely. In case of a remote registry, Docker hub can be considered as a GitHub, which holds docker images instead of repositories. The image might include (lightweight os, application, databases, dependencies and so on).
The default registry is Docker Hub and Docker Cloud, they are public. In order to use them, you should create a user account. 

![](https://i.imgur.com/USFLCpL.png){: .align-center}



credits to [https://deis.com/blog/2016/docker-overview-pt-1/]





