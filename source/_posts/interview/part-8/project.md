---
title:  前端性能优化
date: 2021-12-16 09:30:39
tags: 面试
---


### 前端性能优化


三个方面来说明前端性能优化
一： webapck优化与开启gzip压缩
    1.babel-loader用 include 或 exclude 来帮我们避免不必要的转译，不转译node_moudules中的js文件
    其次在缓存当前转译的js文件，设置loader: 'babel-loader?cacheDirectory=true'
    2.文件采用按需加载等等
    3.具体的做法非常简单，只需要你在你的 request headers 中加上这么一句：
    accept-encoding:gzip
    4.图片优化，采用svg图片或者字体图标
    5.浏览器缓存机制，它又分为强缓存和协商缓存
二：本地存储——从 Cookie 到 Web Storage、IndexedDB
    说明一下SessionStorage和localStorage还有cookie的区别和优缺点
三：代码优化
    1.事件代理
    2.事件的节流和防抖
    3.页面的回流和重绘
    4.EventLoop事件循环机制
    5.代码优化等等

