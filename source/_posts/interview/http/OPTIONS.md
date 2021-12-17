---
title: HTTP 的 OPTIONS 方法 用于获取目的资源所支持的通信选项
date: 2021-12-16 09:30:39
tags: 面试
---

HTTP 的 OPTIONS 方法 用于获取目的资源所支持的通信选项


在 CORS 中，可以使用 OPTIONS 方法发起一个预检请求，以检测实际请求是否可以被服务器所接受。
预检请求报文中的 Access-Control-Request-Method 首部字段告知服务器实际请求所使用的 HTTP 方法；
Access-Control-Request-Headers 首部字段告知服务器实际请求所携带的自定义首部字段。
服务器基于从预检请求获得的信息来判断，是否接受接下来的实际请求。