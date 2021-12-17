---
title: 并发模型与事件循环 Concurrency model and the event loop 
date: 2021-12-16 09:30:39
tags: 面试
---



## 并发模型与事件循环 Concurrency model and the event loop


### 浏览器中的事件循环

- 函数的执行顺序实现：函数调用栈、任务队列(task queue)
- 一个线程中，事件循环是唯一，任务队列可以拥有多个

**任务队列：**

- 宏任务macro-task：
	- script(整体代码)
	- setTimeout
	- setInterval
	- setImmediate
	- I/O
	- UI render
- 微任务micro-task：
	- process.nextTick
	- Promise
	- Async/Await(实际就是promise)
	- MutationObserver(html5新特性)


先执行宏任务，然后执行该宏任务产生的微任务，若微任务在执行过程中产生了新的微任务，则继续执行微任务，微任务执行完毕后，再回到宏任务中进行下一轮循环


node 11:

输入数据阶段(incoming data)
->
轮询阶段(poll)
->
检查阶段(check)
->
关闭事件回调阶段(close callback)
->
定时器检测阶段(timers)
->
I/O事件回调阶段(I/O callbacks)
->
闲置阶段(idle, prepare)
->
轮询阶段(poll)




node io密集型


http无状态协议

webpack  gulp


https://juejin.cn/post/6844904100195205133