---
layout:     post
title:      "Docker实战"
subtitle:   ""
date:       2015-12-24 17:41:00
author:     "lincoln"
header-img: "img/post-bg-01.jpg"
---

# Docker实战

### 安装Docker

    # yum install docker
    
### 验证Docker是否安装正确

    # docker run hello-world
    
执行报错  

    Post http:///var/run/docker.sock/v1.20/containers/create: dial unix /var/run/docker.sock: no such file or directory.
    * Are you trying to connect to a TLS-enabled daemon without TLS?
    * Is your docker daemon up and running?

解决方案  
![issue]({{ site.baseurl }}/img/does_not_start_docker_after_installation.png)

    service docker start

### 再次验证Docker是否安装正确

    # docker run hello-world
    
    Unable to find image 'hello-world:latest' locally
    Trying to pull repository docker.io/library/hello-world ... latest: Pulling from library/hello-world
    3f12c794407e: Pull complete 
    975b84d108f1: Pull complete 
    Digest: sha256:8be990ef2aeb16dbcb9271ddfe2610fa6658d13f6dfb8bc72074cc1ca36966a7
    Status: Downloaded newer image for docker.io/hello-world:latest


    Hello from Docker.
    This message shows that your installation appears to be working correctly.

    To generate this message, Docker took the following steps:
     1. The Docker client contacted the Docker daemon.
     2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
     3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
     4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

    To try something more ambitious, you can run an Ubuntu container with:
    $ docker run -it ubuntu bash

    Share images, automate workflows, and more with a free Docker Hub account:
    https://hub.docker.com

    For more examples and ideas, visit:
     https://docs.docker.com/userguide/

命令未找到hello-world镜像，自动从仓库中下载一个回来。  

下载的镜像元数据保存的位置为:

    /var/lib/docker/graph/
    
每个镜像会生成一个唯一的ID