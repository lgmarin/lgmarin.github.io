---
layout: post
title:  "How to Install and Configure Docker on Linux"
date:   2022-06-24 05:00:00 -0300
categories: docker, containers, mysql, development
---
This article will explain the basics to prepare and run a development instance of MySQL inside a Docker Container. 

## To Containerize, or not to containerize, that is the question

How many times as a developer you got a new project, or even, you are learning something new and you realize that you will need to install some dependencies for that project, let it be a compiler or interpreter for a different language, or a tool or framework or even a database.

To get the idea, imagine that you are working with something that uses a MySQL DB, and then you will need to move to a Postgres DB, or latter, you will do a tutorial on how to integrate a NoSQL DB, like Mongo.

Now you have on your operating system a crazy mess of different softwares that you may or may not use latter on. How you can solve this horrendous mess, yo may ask? Why not with Docker?

## Using a MySQL Docker Container for your projects

Here, we will run through the process on how to configure and run a Docker container to use in your developer projects.

### Pulling the Docker Image

First, you should have the Docker installed and running in your system. Don't have it yet? Take a look at my other [post][install-docker] where I go through the process on how to install and use Docker.

To get the desired image, you should take a look at the [Docker Hub][mysql] website, and verify what is the tag for the version that you want. If you don't mind the version and just want the latest and greatest version, just use the tag last. Here I will use the 8.0 version.

{% highlight shell %}
$ docker pull mysql:8.0
{% endhighlight %}

### Starting the Container

To start your container, it's just a matter of running the following command. But hold on! With this command we are also going to configure some things in our MySQL server.

First, we should take not that the run command will initialize the container with the options and configurations that we want. There a lot of different arguments and options, to see all of them take a look at the [Docker Reference Website][docker-refference].

{% highlight shell %}
docker run --name mysql-dev -p 3306:3306 -e MYSQL_ROOT_PASSWORD=mysqlroot -d mysql:8.0
{% endhighlight %}

In this command, we are using the option --name mysql-dev to specify the name that we want for our container. 

The -p 3306:3306 is used to map the internal port of the container to our local network. If you want to use a different port, change to -p 4545:3306, note that the first port is the external port, that will use in our hosting system, that is being mapped to 3306, the default MySQL server port inside the container.

The -e Argument, set the Environment Variables for the container, in this case, we are setting the password for the root user. If you remove the argument -e MYSQL_ROOT_PASSWORD=mysqlroot, the MySQL initialization scripts will create a default password for the root user, to find that password you could use the following command to search inside the logs for the password.

{% highlight shell %}
docker logs learn-mysql-docker | grep &quot;GENERATED ROOT PASSWORD:&quot;
{% endhighlight %}

Finally, the -d mysql:8.0 argument specify the Docker image and the tag to run.



[docker]: https://www.docker.com/
[docker-refference]: https://docs.docker.com/engine/reference/run/
[mysql]: https://hub.docker.com/_/mysql?tab=tags