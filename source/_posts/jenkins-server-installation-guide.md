---
title: Jenkins Server Installation Guide
date: 2017-02-17 12:09:49
categories: DevOps
tags: 
  - CI
  - Jenkins
---

### Server Environment

- OS: Ubuntu 16.04
- Java: v1.8 

### Install Java 1.8

    $ sudo add-apt-repository ppa:webupd8team/java 
    $ sudo apt-get update 
    $ sudo apt-get install oracle-java8-installer

> <http://stackoverflow.com/questions/30177455/moving-from-jdk-1-7-to-jdk-1-8-on-ubuntu>


### Next step

1. {% post_link jenkins-master-node-installation-guide %}
2. Jenkins Slave Agent Node Installation Guide
3. Jenkins Build-up a task

