--------------
layout: single
title:  "Docker Installation and Usage"
categories: Cloud
comments: true
---------------

This article aims to give you the basic skills required to build Docker containers. A general understanding about Docker might be useful to connect concepts together. If you don't know what is Docker, please review [Docker intro](http://localhost:4000/cloud/into-docker/).

Transforming to Docker is a wise decision for most companies, Docker efficiently enhances their performance and scalability at low cost.

Lets put the use of Docker into a real example: an enterprise that runs an Airline reservation system, they use many services such as scheduling, fare tariffs, passenger reservation records..etc. This system receives thousands of daily requests. They probably deploy their software across many nodes/computers on the cloud, each computer runs a service.

Suppose they have 3 services and they want to run each one on 5 nodes, which means they will ire 3*5 nodes for the entire application. This will add layers of network overhead and more cost.  Docker containers can be a good alternative. Since containers separate applications within the same machine, they may use 5 nodes with 3 containers to resolve the issue. Each container runs a copy of a single service.
Developers also take advantage of working with containers, they can easily test their application while having all services work together using [CI](https://en.wikipedia.org/wiki/Continuous_integration). 


**Table of Content**

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



## Docker installation

Docker has two software editions; the community (CE) which is free, and the enterprise (EE) which is paid and comes with support. This guide is mainly about Docker CE.

The following will show in details how to Docker on both Linux and Windows. Note that I've tested the installation on both Linux (Ubuntu) and Windows 7. Please, feel free to share your experience with other operating systems.


### Install Docker on Linux


Docker containers are mainly built for Linux, hence installing docker containers on Linux is a straightforward process.
Docker documentation includes enough details about installation on different platforms. Pick the method that matches your system, and please make sure:

- To have 64bit OS
- Install docker from its official source


If you didn't install Docker before, the easiest way is using **get-docker** script which will install the latest Docker edge release. This way will automatically detect your system and install the suitable Docker accordingly.


Please note this installation is convenient for the development and testing purpose. In the case of production, you need to set up a stable docker manually by referring to [Docker documentation](https://docs.docker.com/install/).

Download the script file from [get.docker.com](https://get.docker.com/) by writing the following commands into the terminal:

```
$ curl -fsSL get.docker.com -o get-docker.sh
```


Then enter your sudo password

![](https://i.imgur.com/s9QfEG2.png)


If the installation went ok, you will see the following image


![](https://i.imgur.com/F8FYMQ3.png)



Add your user to Docker group as shown in the image 

![](https://i.imgur.com/0TiPlrK.png)


Make sure Docker installed properly:

![](https://i.imgur.com/SvgljSi.png)



You need to install two more tools which are essential to work with Docker. Docker-machine and Docker- compose. 

**Installing Docker-machine**

"[Docker Machine](https://docs.docker.com/machine/overview/) is a tool that lets you install Docker Engine on virtual hosts, and manage the hosts with docker-machine commands."

Go to [the site](https://github.com/docker/machine/releases/), scroll down to Linux and copy the installation commands, and paste it to the terminal, see the images below.


![](https://i.imgur.com/Cn7Cn1w.png) 

![](https://i.imgur.com/nahT2Rs.png)
 


**Test Docker-machine**

![](https://i.imgur.com/JPAiiES.png)


**Installing Docker-Compose**

"[Docker-compose](https://docs.docker.com/compose/overview/) is Compose is a tool for defining and running multi-container Docker applications."

Check the last compose release from [Docker Github](https://github.com/docker/compose/releases/), copy Linux installation command and paste it into the terminal, in case you faced a permission failure, just add sudo at the beginning

![](https://i.imgur.com/V0vuLO1.png)
 
![](https://i.imgur.com/4mWbQh9.png)


**Test Docket-compose**

![](https://i.imgur.com/uDtYxO8.png)


### Installing Docker on Windows

In windows you have two options:

- Install docker for windows, which is feasible only for Windows 10 enterprise/professional and windows server 2016.
- Install Docket Toolbox for Windows 7/8 and Windows 10 Home edition.



I will show the steps for installing Docker Toolbox in windows 7. To start: 

- visit [Docker store](https://store.docker.com/) and click on Docker CE
- locate Docker commuinty editoin for Windows.

![](https://i.imgur.com/sw6Lcow.png) 

![](https://i.imgur.com/uJ0UCMf.png) 

![](https://i.imgur.com/zEKBi11.png)


Click on Docker Toolbox, and install it as shown in the images bellow:

**Note:** make sure to remove virtualbox, Gitbash as these are packaged within Docker Toolbox.


![](https://i.imgur.com/bphiyd5.png)   

![](https://i.imgur.com/nrcBTZb.png){: .align-center}


After installation, run Docker quick starter in the Desktop, this will setup Docker machine and compose and all related softwares.

![](https://i.imgur.com/sqGWLHO.png){: .align-center}

Test If Docker installed properly.

![](https://i.imgur.com/6amQ1pT.png)


Test Docker-machine and Docker-compose

![](https://i.imgur.com/yLfUoSq.png)


**Note:** working in Windows 7 cmd might not effcient; thus, you can install an advanced bash terminal as [cmder.net](http://cmder.net/), which is free.


## Docker Main Terminologies

Image: a collection of files (read-only), files are structured as layers. From an object-oriented paradigm, an image is a class
Container: Set of processed running from the image, containers are created from images. container can be considered as an instance of an image
Host:     The machine that Docker installed on
Registry: storage of Docker images


It is very important to differentiate between containers and images, and how Docker effciently utilize machine resources.

Some critical questions you should be able to answer:

- What happens when we create an image?
- What happens when we create a container?
- What happen when we change the container, do we also change the image?
- How to make the image we created availbale to the public?


Docker images are constructed as layers, the first image is called the base image, such as a lightweight Linux system as [Alpine](https://alpinelinux.org/). When you create a new image, Docker file system only adds the changes as a new layer to the base image, and so on. 
This is because images are read-only and at the same time this method reduces time and storage space. 
Docker demonstrates this by using a special file system with [Copy-on-write technique](https://docs.docker.com/storage/storagedriver/).

When you change the container, you actually add a new writable layer on the top of the image, your changes won't persist if you delete the container, in order to store the changes, you need to commit them and the change will be added into the image layered structure.
The image below shows Docker file system.

![](https://nvisium.com/articles/2014/2014-10-15-docker-cache-friend-or-foe/docker-filesystems-multilayer.png)


## Docker Commands 

```
> docker version       (Shows the installed Docker version)


> docker info          (gives information about Docker)


> docker login         (Login using Docker Hub credentials)


> docker images        (list all local images)


> docker ps            (show running ontainers)


> docker ps -all       ( show all containers even the stoped ones)

```

```
> docker run  <image> 
```

The previous command does the following: 

- look for the image in the image cache, if it does not exist, pull it from Docker hub
- build a container based on the image
- setup virtual IP for container and forward request from 80 port in host to container
- start the container by running the cmd command in Dockerfile.


```  
> docker start <container name|id>                            (start a paused container)

> docker stop <container name|id>                             (stop a running container)

> docker rm  <container name|id>	                          (remove a container, after removing, you need to run it from the image again)

> docker build -t <username/imagename> <localtion>            (build an image from Dockerfile)

> docker rmi <image name|id>                                  (force remove image locally)

> docker commit -a <auther name> <container-id> <image-name>  (create an image from a running container)
```

## Build a Simple Docker Image

Let's try the previous commands, and build a real Docker container, the scenario consists of the following:

- build a Docker image (simple flask app)
- run docker container from the built image
- Push the image to docker hub


First, you need to create a Docker hub account such that you can upload images as well as pull images from there.

Go to the [Docker hub](https://hub.docker.com/) and create a new account:

```
> docker login
```
Then enter your Docker hub credentials


**Build a docker image**

Create a simple flask app, you can download a demo from [here](https://github.com/nadaa/FlaskApp-container)

The folder includes:

- app.py                    (server flask application to handle a get request)
- requirements.txt          (a list of required dependencies, which will be installed automatically during the build)
- Dockerfile                (a Docker configuration to build images from scratch)



**Note:**
I used **"nadadocker"** which is my Docker Hub username, you should replace it with yours. In addition, **"flaskapp"** is the name of the image,
you are free to choose any name, but make it meaningful in case you will publish publicially via Docker Hub.

In order to create a new image from the flask application, we need to prepare a **Dockerfile**. It's a text file, contains image configurations, such as the base image, ports, commands,..etc). Here, we will use simple Dockerfile configuration.
There are two kinds of images in Docker: base image and child image. A new image always is established from a base image. For example, the container bellow uses python:3-onbuild as a base image since the application is written in python.


```
.......Dockerfile...........
FROM python:3-onbuild
EXPOSE 5000
CMD ["python", "./app.py"]
............................

```
**FROM :**  contains the base image (the application needs python, so it will be added to the image, as well as all dependencies in **requirements.txt** and **pip**,..,etc )

**EXPOSE :** this is to tell docker about application port (flask uses port 5000) 

**CMD :** Commands used to run the application


cd to the path of your application that you want to create an image based on, such that Dockerfile will be visible for the build command.

```
> docker build -t  nadadocker/flaskapp .

```
**Note:** the dot indicates the current location, which leads to the Dockerfile.

![](https://i.imgur.com/TxY1lfC.png)  

![](https://i.imgur.com/x7fRzVd.png)


**Run the Container**

```
> docker run --name myflask -p 8800:5000 nadadocker/flaskapp
```

Open the browser and check the app at localhost:8800, you should see the following image

![](https://i.imgur.com/177hZR3.png)



### Push the image into Docker Hub

![](https://i.imgur.com/e6jTn2I.png)



Now, lets check if we can use the online version of the nadadocker/flaskapp, I am going to remove the current running container as well the local image from the cache.


```
> docker rm myflask

> docker rmi nadadocker/flaskapp

> docker run --name myflask -p 8800:5000 nadadocker/flaskapp
```


Now open the brower and check if the application works.


In case you make changes to the container, and you want to reflect the changes into the images, you just need to use commit command. Let's assume we updated the running container by added some libraries. 


```
> docker commit <container id| name> <repository name>/<your image name>
```
Way to go, this was your first Docker container,I hope you find it useful. If not, please let me know how to improve it further.
The next article will focus on configuring Dockerfile, working with multiple containers and networking. 









