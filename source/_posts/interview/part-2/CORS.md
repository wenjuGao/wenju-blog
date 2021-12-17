---
title: 跨域
date: 2021-12-16 09:30:39
tags: 面试
---


### 跨域


因为浏览器出于安全考虑，有同源策略。也就是说，如果协议、域名或者端口有一个不同就是跨域，Ajax 请求会失败。
为来防止CSRF攻击
1.JSONP
    JSONP 的原理很简单，就是利用 \<script\> 标签没有跨域限制的漏洞。
    通过 &lt;script	&gt; 标签指向一个需要访问的地址并提供一个回调函数来接收数据当需要通讯时。

```htm
<script src="http://domain/api?param1=a&param2=b&callback=jsonp"></script>
<script>
    function jsonp(data) {
    	console.log(data)
	}
</script>
```


JSONP 使用简单且兼容性不错，但是只限于 get 请求。

2.CORS
    CORS 需要浏览器和后端同时支持。IE 8 和 9 需要通过 XDomainRequest 来实现。
3.document.domain
    该方式只能用于二级域名相同的情况下，比如 a.test.com 和 b.test.com 适用于该方式。

    只需要给页面添加 document.domain = 'test.com' 表示二级域名都相同就可以实现跨域
4.webpack配置proxyTable设置开发环境跨域
5.nginx代理跨域
6.iframe跨域
7.postMessage
    这种方式通常用于获取嵌入页面中的第三方页面数据。一个页面发送消息，另一个页面判断来源并接收消息


XDomainRequest是在IE8和IE9上的HTTP access control (CORS) 的实现，在IE10中被 包含CORS的XMLHttpRequest 取代了，如果你的开发目标是IE10或IE的后续版本，或想要支待其他的浏览器，你需要使用标准的HTTP access control。