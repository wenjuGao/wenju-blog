---
title: Vue的通信形式
date: 2021-12-16 09:30:39
tags: 面试
---

## Vue的通信形式

1. $emit、props

父子组件间通信最常使用的通讯形式：
	- 子组件props中接收父组件传递下来的数据
	- 子组件通过$emit向父组件传递事件

2. $root、$parent、$children、$refs

通过$root、$refs可以得到当前组件实例
通过$parent、$children分别可以到达父级组件实例和子组件实例，进而得到不同组件的data和methods中是event进而修改data


该方法虽然可以实现逻辑，但是因为是通过操纵实例直接对数据进行修改，会使项目修改数量的逻辑不好追踪，增加项目维护难度
在 3.x 中，$children property 已移除

3. provide、inject

涉及数据传递层级较多的时候使用，在多层children组件中注入数据，类似于跨层级的props

4. eventBus
