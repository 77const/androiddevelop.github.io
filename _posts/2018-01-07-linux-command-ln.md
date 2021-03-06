---
layout: post
title: 'Linux命令之ln'
date: '2018-01-07'
header-img: "img/post-bg-unix.jpg"
tags:
     - java
author: 'Codeboy'
---

## 背景

这几天一直想更换下osx下用户家目录的名字，为什么要更换呢? 因为之前托同学帮忙买来mac的时候已经创建了用户，当时也懒，也没用过osx，所以就一直到现在了。公司里的电脑是另外一台Macbook Pro，每次有一些牵扯到绝对路径的脚本等内容使用时，都需要改动配置等，于是乎决定对自己这台mac进行家目录重命名，大概的操作如下:

```
系统设置 -->  用户和组 --> 解锁左下角小锁 --> 右击列表中用户 --> 高级选项 --> 修改家目录
```

关于家目录的修改这里不做详细介绍， 网上有很多教程，不过请做好数据备份。路径修改后，希望能通过访问新的路径访问到原先家目录对应的文件，毕竟各种软件的配置等信息都还在，这时候就需要用上Linux中ln命令。

## ln命令简介
ln是link的缩写，可以用来创建软连接和硬连接，使用和特点如下：

#### 软链接：

使用操作:	`ln -s source target`

1. 软链接以路径的形式存在, 类似于Windows操作系统中的快捷方式
2. 软链接可以跨文件系统, 硬链接不可以
3. 软链接可以对一个不存在的文件名进行链接
4. 软链接可以对目录进行链接

#### 硬链接：

使用操作:	`ln source target`

1. 硬链接以文件副本的形式存在, 但不占用实际空间。
2. 不允许给目录创建硬链接
3. 硬链接只有在同一个文件系统中才能创建

> 更多其他参数的使用，可以`man ln`

## 使用

既然家目录改变了，可以将新的家目录连接的旧的家目录即可解决问题

	ln -s old_home new_home
	
## 后记
两台mac的家目录统一了，很多文件、项目等的配置不用做任何修改了，哈哈。


> 如有任何知识产权、版权问题或理论错误，还请指正。
>
> 转载请注明原作者及以上信息。
