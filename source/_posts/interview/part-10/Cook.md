---
title: cookie跨域共享
date: 2021-12-16 09:30:39
tags: 面试
---



cookie跨域共享

document.cookie = newCookie;

newCookie是一个键值对形式的字符串：
1. name **(必要)** ：要创建或覆盖的cookie的名字
1. value **(必要)** ：cookie的值
1. end **(必要)** ：最大年龄的秒数 (一年为31536e3， 永不过期的cookie为Infinity) 
1. path **(可选)** ：如果没有定义，默认为当前文档位置的路径
1. domain **(可选)** ：如果没有定义，默认为当前文档位置的路径的域名部分，如果指定了一个域，那么子域也包含在内
1. max-age **(可选)** =max-age-in-seconds 过期时间
1. expires **(可选)** =date-in-GMTString-format 如果没有定义，cookie会在对话结束时过期
1. secure **(可选)**  (cookie只通过https协议传输)