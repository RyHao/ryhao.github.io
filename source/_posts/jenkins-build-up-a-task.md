---
title: Jenkins Build-up a task
date: 2017-02-20 12:11:01
categories: DevOps
tags: 
  - CI
  - Jenkins
---

------

<!-- more -->

### Click 新增作業

![New Job](images/click-new-job.png)

### 建置 free style 專案

![Free Style Project](images/free-style.png)

### 原始碼管理 - Git

1. Put private key in Crediential
3. Put public key in gitlab

#### How to gen key

    ssh-keygen -t rsa -C "test@climax.com.tw"

    pub: cat ~/.ssh/id_rsa.pub

    private: cat ~/.ssh/id_rsa

><http://10.1.2.150:53180/help/ssh/README>

#### Add Credentials Keys

![Add Credentials](images/add-key-1.png)

Domain: Global credentials (unrestricted)

Kind: SSH Username with private key

Username: jenkins

Privae Key: From the Jenkins master ~/.ssh

![Add Credentials](images/add-key-2.png)

#### Set the repository URL and change the ssh key

![Git](images/git-source.png)

### Build Trigger

![Build Trigger](images/build-trigger.png)

### 建置環境 (case by case)

![Build Env](images/build-env.png)

### 建置和建置後動作 (case by case)

![Build Setting](images/build-setting.png)

