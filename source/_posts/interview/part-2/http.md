---
title: http协议简介
date: 2021-12-16 09:30:39
tags: 面试
---


### http协议简介


http1.0，http1.1，http2.0，https，websocket/ http无状态协议

常见状态码

HTTP 响应中包含一个状态码，用来表示服务器对客户端响应的结果。
状态码一般由3位构成：

1xx : 表示请求已经接受了，继续处理。
2xx : 表示请求已经处理掉了。
3xx : 重定向。
4xx : 一般表示客户端有错误，请求无法实现。
5xx : 一般为服务器端的错误。

比如常见的状态码：

200 OK 客户端请求成功。
301 Moved Permanently 请求永久重定向。
302 Moved Temporarily 请求临时重定向。
304 Not Modified 文件未修改，可以直接使用缓存的文件。
400 Bad Request 由于客户端请求有语法错误，不能被服务器所理解。
401 Unauthorized 请求未经授权，无法访问。
403 Forbidden 服务器收到请求，但是拒绝提供服务。服务器通常会在响应正文中给出不提供服务的原因。
404 Not Found 请求的资源不存在，比如输入了错误的URL。
500 Internal Server Error 服务器发生不可预期的错误，导致无法完成客户端的请求。
503 Service Unavailable 服务器当前不能够处理客户端的请求，在一段时间之后，服务器可能会恢复正常。