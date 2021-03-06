---
layout: post
title: "git 学习笔记（1）"
date: 2020-06-08 11:45:12 +0800
categories: notes
tags: git
img: https://www.z4a.net/images/2020/06/10/u4248224721330618640fm26gp0.jpg
---
git 版本控制

## 版本控制简介

https://www.z4a.net/images/2020/06/10/u4248224721330618640fm26gp0.jpg
工程设计领域中使用版本控制管理工程蓝图的设计过程。在IT开发过程中也可以 使用版本控制思想管理代码的版本迭代。

## 版本控制工具应该具备的功能

### 协同修改

多人并行不悖的修改服务器端的同一个文件。
### 数据备份

不仅保存目录和文件的当前状态，还能够保存每一个提交过的历史状态。
### 版本管理

在保存每一个版本的文件信息的时候要做到不保存重复数据，以节约存储空间，提高运行效率。这方面SVN采用的是增量式管理的方式，而 Git 采取了文件系统快照的方式。
### 权限控制

对团队中参与开发的人员进行权限控制。

对团队外开发者贡献的代码进行审核——Git 独有。
### 历史记录

查看修改人、修改时间、修改内容、日志信息。
	
将本地文件恢复到某一个历史状态。
### 分支管理

允许开发团队在工作过程中多条生产线同时推进任务，进一步提高效率。


## 版本控制工具


### 集中式版本控制工具

CVS、SVN、VSS……

![集中式](https://www.z4a.net/images/2020/06/09/e64c1756e63dd0b7552cf9cb9578bd80.png)

每一个开发人员是一个客户端，文件和版本信息存储在服务器端；如果服务器宕机了，则会造成文件丢失，而客户机上只会保存当前的数据，以前的历史数据都不存在了。会造成`单点故障`的问题。

### 分布式版本控制工具：

Git、Mercurial、Bazaar、Darcs……

![分布式](https://www.z4a.net/images/2020/06/09/f1d1cbebfb1e170356467ab726cbe9c2.md.png)

以git为例，分布式版本控制工具会使得每个开发人员在本地就可以进行版本控制，可以有效的避免单点故障。