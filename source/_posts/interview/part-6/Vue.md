---
title: vue和react的区别
date: Vue响应式原来
tags: 面试
---


## Vue

1. Vue响应式原来

- 组件初始化的时候，先给每一个Data属性都注册getter，setter，也就是reactive化。
- data中的数据分别new一个Watcher对象，此时watcher会立即调用组件的render函数去生成虚拟DOM
- 在调用render的时候，就会需要用到data的属性值，此时会触发getter函数，将当前的Watcher函数注册进sub里
- 当data属性发生改变之后，就会遍历sub里所有的watcher对象，通知它们去重新渲染组件