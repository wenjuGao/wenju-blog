---
title: websocket简介
date: 2021-12-16 09:30:39
tags: 面试
---



### websocket简介


websocket 握手过程
	- 客户端向服务器发送一个SYN J
	- 服务器向客户端响应一个SYN K，并对SYN J进行确认ACK J+1
	- 客户端再想服务器发一个确认ACK K+1