---
title: 同源策略
date: 2021-12-16 09:30:39
tags: 面试
---


## 同源策略

### 1. 同域, 同协议, 同端口:

- 同域即host相同, 顶级域名, 一级域名, 二级域名, 三级域名等必须相同, 且域名不能与 ip 对应;
- 同协议要求, http与https协议必须保持一致;
- 同端口要求, 端口号必须相同.

注：（IE有些例外, 它仅仅只是验证主机名以及访问协议，而忽略了端口号.）


### 2. 限制

- iframe限制：可以访问同域资源, 可读写;访问跨域页面时, 只读.
- Ajax限制
- Script无限制

### 3. 跨域
- 使用代理，web服务器代理转发
- JSONP，回调本地js方法，返回值用参数形式传递
- postMessage实现跨文本档、多窗口、跨域消息传递
	postMessage(data,origin)
	addEventListener('message',{data,source,origin}){}
	- data, 表示父页面传递过来的message
	- source, 表示发送消息的窗口对象
	- origin, 表示发送消息窗口的源(协议+主机+端口号)
```javascript
// send
window.frames[0].postMessage('message', origin)
// get
window.addEventListener('message',function(e){
    if(e.source!=window.parent) return;//若消息源不是父页面则退出
      //TODO ...
});
```
- CORS 跨域访问


### CORS 跨域访问

1. 简单请求(HEAD、GET、POST)

- 浏览器会自动在请求的头信息加上 Origin 字段
- 服务端允许
	如果要发送Cookie，Access-Control-Allow-Origin就不能设为*，必须指定明确的、与请求网页一致的域名
- 服务端拒绝
	当然我们为了防止接口被乱调用，需要限制源，对于不允许的源，服务端还是会返回一个正常的HTTP回应，但是不会带上 Access-Control-Allow-Origin 字段，浏览器发现这个跨域请求的返回头信息没有该字段，就会抛出一个错误，会被 XMLHttpRequest 的 onerror 回调捕获到。
这种错误无法通过 HTTP 状态码判断，因为回应的状态码有可能是200


1. 非简单请求(PUT、DELETE)
- 预检请求(OPTIONS)
- 浏览器的正常请求和回应



参考：
[一次弄懂跨域问题](https://segmentfault.com/a/1190000017579464)