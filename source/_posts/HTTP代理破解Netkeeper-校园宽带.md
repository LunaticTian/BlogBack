---
title: HTTP代理破解Netkeeper(校园宽带)
tags:
  - 杂碎
  - 鼓捣
abbrlink: 43b594a8
date: 2018-10-07 22:17:38
---

## 先行条件

理论支持

- Shadowsocks
- VPN
- HTTP代理


![](http://cdn.lunatic.wang/qq.png)

<!--more-->

### 必备条件

- 相同内网环境
	- 1.设备能够相互ping通
	- 2.在同一局域网关

-	某一个设备能够上网

### 适合场景

- 适应各类校园网环境

理论上适合各类网络环境

### 原理

基于HTTP代理方式共享，Netkeeper等软件只屏蔽wifi共享类软件并不屏蔽代理，所以基于此通过内网共享网络。

### 准备工作
- [CCProxy](http://www.ccproxy.com/)(Windows端HTTP代理软件)
- [Proxifier](http://www.proxifier.com/)(全局代理工具)
- 能够上网的PC设备



## 开始工作

*PS：登陆校园网端统称：有网端，为联网端称：无网端*

### 测试ping

查看双方内网ip,并相互ping

> CMD 

> $ ipconfig /all



![](http://cdn.lunatic.wang/bijibencmd.jpg)


![](http://cdn.lunatic.wang/zhujiIP.PNG)

> CMD

> $ ping 100.64.98.103

![](http://cdn.lunatic.wang/zhujiping.PNG)

> CMD

> $ ping 100.64.203.33 

![](http://cdn.lunatic.wang/xiugaibijibenping.jpg)

若出现某一方无法正常ping通，则检查防火墙设置，具体为：打开防火墙设置，防火墙高级，入站规则，启动**文件和打印机共享(回显请求)**。

![](http://cdn.lunatic.wang/xiugaifanghuoqiang.PNG)


### 开启CCProxy

在有网端操作：

1. 安装CCProxy
2. 点击设置
3. 请选择本机局域网ip(也可选择*自动检测*)
![](http://cdn.lunatic.wang/xuanzeip.png)

至此完成HTTP代理的架设。

若有网端启动Shadowsocks，则CCProxy修改socks的端口。

### 开启Proxifier

此步作用为全局代理软件，所有软件都可连入互联网，若只需浏览网页则：

![](http://cdn.lunatic.wang/ceshi.png)


开启Proxifier：

1. 安装Proxifier
2. 打开Proxifier，点击代理服务器,点击编辑填写ip以及端口
![](http://cdn.lunatic.wang/peizhiProxifier.png)
3. 点击代理规则，在目标主机中加入被代理的ip
![](http://cdn.lunatic.wang/bianxieguize.png)
加入目标主机的原因是CMD或者GIT能够联网。


## 移动端

###Android

安卓需要下载ProxyDroid进行搭配。

需求：

- root
- Android8.0以下

[教你在Android手机上使用全局代理！](https://blog.csdn.net/testcs_dn/article/details/78526468)

### ios

不建议ios端进行全局配置。



[iOS 全局代理](https://blog.huguotao.com/post/iOS-proxy)

## 完成

![](http://cdn.lunatic.wang/qq.png)


