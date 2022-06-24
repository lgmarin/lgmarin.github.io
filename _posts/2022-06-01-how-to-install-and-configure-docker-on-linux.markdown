---
layout: post
title:  "How to Install and Configure Docker on Linux"
date:   2022-06-01 05:00:00 -0300
categories: docker, containers, linux
---
This article aims to explain the basics of Containers and Docker. With a tutorial on how to install and prepare to use Docker Container in a Linux and Windows Environment. 

## What is Docker and Containers? And Docker Containers? 

Virtualization is far from being a new subject in the development world and the same can be said about Containerization. There are some similarities on both of these approaches, but there are some differences.

The main difference between a Container and a Virtual Machine can be related to the size and velocity of execution. As the VM has a full blown Operating System running on top of a virtualized environment or a Hypervisor, a Container can be very small, as it runs on top of another Operating System over a Container Engine, with only the necessary libraries to run the application that is being containerized.

[![Docker vs Virtual Machine Architecture](/images/posts/dockervscontainer.png)](https://docs.microsoft.com/en-us/dotnet/architecture/containerized-lifecycle/what-is-docker)

[Docker][docker] is a platform to develop, manage and execute containers, allowing them to run those containers in different environments on different Operating Systems.

## Installing Docker on Linux

The binaries from Docker are widely available in all the main distributions.

### On Arch Linux or based Distros

First you should check for updates and install the docker and docker-compose packages.

{% highlight shell %}
$ sudo pacman -Syu
$ sudo pacman -S docker docker-compose
{% endhighlight %}

To allow your user to run the docker cli commands without using sudo, just run the following command in the terminal. After that you should restart your system so the configuration takes effect and you will be able to run the docker cli without the need to elevate your user privileges.

{% highlight shell %}
$ sudo usermod -aG docker $USER
{% endhighlight %}

Finally, you should enable and start the services for docker, so it will run automatically every time you start your OS.

{% highlight shell %}
$ sudo systemctl enable docker.service
$ sudo systemctl start docker.service
{% endhighlight %}

To check if everything is ok, run the following command in the terminal.

{% highlight shell %}
$ docker version
{% endhighlight %}

## Running Docker and Most Used Commands

Following I will list the main command syntax that allows you to perform the most used operations with Docker.

### Search for Docker Images

If you wish, you can use a web browser and search for the desired image, just go to the [Docker Hub][docker-hub] page and you can see the various images that you can use for your projects. This page is also good, to look for information about the images.

If you are a true brave dev you can also use your trustful Terminal Emulator, with the following syntax by replacing the <name> for your desired image.

{% highlight shell %}
$ docker search <name>
{% endhighlight %}

### Get a Docker Image

To get an image that you looked through the search command or in [Docker Hub][docker-hub].

{% highlight shell %}
$ docker pull <image>
{% endhighlight %}

If you don't specify a version, usually Docker will pull the latest version of the image. To specify the version you can use a tag that you can find on the hub page for the image. For example, if you want the version 8.0 of the [mysql][mysql] image, you should run.

{% highlight shell %}
$ docker pull <image>:<tag>

$ docker pull mysql:8.0
{% endhighlight %}

### List Images

To list all images in your system.

{% highlight shell %}
$ docker images
{% endhighlight %}

### Remove Images

To remove an image from your system, specify the image id that you should find with the help of the command above, or use the name followed by the tag, separated by semicolon.

{% highlight shell %}
$ docker rmi <image id>
$ docker rmi <image>:<tag>
{% endhighlight %}

### Run a Docker Container

To run a Docker container, simply use the syntax run followed by the image name.

{% highlight shell %}
$ docker run <image>
{% endhighlight %}

### Start, Stop and Restart a Docker Container

During the first run, the Docker Daemon will create the volumes and all the configuration used to run the container. After that you should start, stop, and restart the container with the following commands.

{% highlight shell %}
$ docker start <container>
$ docker restart <container>
$ docker stop <container>
{% endhighlight %}

### List Containers

To list your containers you will use the command ps, it will return just the ones that are running at the moment, if you want to see all, even the stopped ones, attach the -a or –all option.

{% highlight shell %}
$ docker ps
$ docker ps -a
{% endhighlight %}

### Remove Containers

To remove a container, run the rm command. If you also want to remove it's attached subvolume, use the argument -v.

{% highlight shell %}
$ docker rm <container>
$ docker rm -v <container>
{% endhighlight %}

That’s a lot to process already! In the next post, I will show a more in depth tutorial on how to use Docker Containers to help in the development process. Imagine that you have different projects to work on, each with a different Database or different services that you should install on your machine, as you guessed and probably faced, things can get out of hand pretty quick. 

With Containers, we could use different versions side by side, we can use a MySQL, a PostgresSQL or even MSSQL DB during or development, and connect our application to the DB server running inside a container. After our development or tests, we just simply stop the container and move on, no crazy dependencies in our OS, no garbage left behind, just a clean DEV environment.

In another article I will also go through the process of creating a Docker file to containerize an application and use Docker Compose to create a multi container environment that is suited for deployment.

Until next time!


[docker]: https://www.docker.com/
[docker-hub]: https://hub.docker.com/search?q=
[mysql]: https://hub.docker.com/_/mysql?tab=tags