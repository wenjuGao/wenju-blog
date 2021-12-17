---
title: 封装JSONP
date: 2021-12-16 09:30:39
tags: 面试
---

## 封装JSONP

```javascript
		function callbackFn(resp) {
			console.log('resp', resp)
		}
		window.callbackFn = callbackFn
		let scriptDom = document.createElement('script')
		scriptDom.src = 'http://suggest.taobao.com/sug?code=utf-8&q=卫衣&callback=(function(arg){callbackFn(arg, 1)})'
		document.getElementById('app').append(scriptDom)
```


参考
[原生JS简单封装JSONP跨域获取数据](https://my.oschina.net/u/4407103/blog/4262669)
[理解JSONP原理与使用](https://bibodeng.com/2013/10/10/%E7%90%86%E8%A7%A3JSONP%E5%8E%9F%E7%90%86%E4%B8%8E%E4%BD%BF%E7%94%A8/)