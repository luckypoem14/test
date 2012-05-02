---
layout: post
title: Goagent 访问github
description:
- Goagent 访问github
categories:
- git
tags:
- github
---
网上文章  在windows上通过代理访问github.com
关键词
git:// 协议 cygwin socat

connect.exe

https:// 协议 http(s) proxy

另外一篇文里涉及另一个软件  corkscrew

##我的办法
####GoAgent代理,直接https操作

#### _netrc文件
machine github.com

login zhangthe9
password xxxxxxxx

machine github.com
login ddatsh
password xxxxx

####git remote add
`git remote add origin git@ddatsh.github.com:ddatsh/blog.git`
改成
`git remote add origin https://ddatsh@github.com/ddatsh/blog.git`

####git config http.proxy
`git config http.proxy http://127.0.0.1:8087/`