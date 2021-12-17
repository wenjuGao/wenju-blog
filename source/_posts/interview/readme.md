---
title: 面向面试编程
date: 2021-12-16 09:30:39
tags: 面试
---

##  面向面试编程

### part-1:html基础（DOM，BOM）

1. [DOM事件的绑定的几种方式](./part-1/dom-bindEvent.md)
	 1. DOM中绑定
	 1. JavaScript获得DOM后绑定
	 1. 事件监听:addeventlistener-removeListener、attachEvent-detachEvent(兼容IE) 
1. html5 新增了哪些标签、废除了哪些标签
1. [node节点查询](./part-1/domNode.md)


---

### part-2:http

1. [http协议简介](./part-2/http.md)
2. [http协议演进](./part-2/Evolution.md)
2. [TCP-UDP及其他应用层协议](./part-2/OPTIONS.md)
2. [http-OPTIONS](./part-2/OPTIONS.md)
2. [跨域](./part-2/CORS.md)
2. [websocket简介](./part-2/websocket.md)
1. load、DOMContentLoaded执行顺序

---
### part-3:javascript基础 

1. [深拷贝、浅拷贝及枚举api](./part-3/Copy.md)
1. [判断数据类型](./part-3/DataType.md)
1. [js事件序(event loop)列及宏任务、微任务，枚举常见的宏任务微任务](./part-3/EventLop.md)
1. [闭包](./part-3/Closure.md)
1. [js中的this，bind、call、apply](./part-3/This.md)
1. [原型链与继承](./part-3/Prototype.md)
1. [Promise](./part-3/Promise.md)
1. [防抖和节流](./part-3/debounce-throttle.md)
1. [EventEmitter](./part-3/EventEmitter.md)
1. [双向绑定](./part-3/proxy.md)
1. [观察者模式-发布订阅者模式](./part-3/Subscribe.md)
1. [vuex异步action、同步mutations](./part-3/Action-mutations.md)
1. 原型链：构造函数、对象
1. 继承模式、工厂函数、函数柯里化
1. [模块化的演进](./part-3/Module.md)
1. [es6常用API](./part-3/Es6.md)
1. [封装JSONP](./part-3/jsonp.md)
1. [JavaScript 异步编程原理](./part-3/异步编程原理.md)
1. [回调函数](./part-3/Callback.md)
1. [函数柯理化](./part-3/Curry.md)

---

### part-12:typescript基础 

1. [interface和type](./part-12/interfaceType.md)
	- interface是接口type是类型别名
	- interface可以extends，但type是不允许extends和implement
	- type可以声明 基本类型，联合类型，元组 的别名，interface不行
	- type 语句中可以使用 typeof 获取类型实例

---
### part-4:css及css预编译

1. flex布局
1. css盒子模型及box-sizing
1. 上下左右居中
1. 像素单位、真实像素
1. sticky
1. [0.5px边框](./part-4/halfPx.md)
1. transform 的 rotate translateX 先后顺序有何不同
1. Retina 屏幕 1px 边框问题（https://juejin.cn/post/6844903456717668359）
1. 块级格式化上下文:BFC:
	- 它是一个独立的渲染区域，只有Block-level box参与， 它规定了内部的Block-level Box如何布局，并且与这个区域外部毫不相干。
	- BFC是一个独立的布局环境，其中的元素布局是不受外界的影响，并且在一个BFC中，块盒与行盒（行盒由一行中所有的内联元素所组成）都会垂直的沿着其父元素的边框排列

---

### part-5:编译工具webpack、gulp

1. webpack编译过程：
	- 初始化参数：从配置文件和 Shell 语句中读取与合并参数，得出最终的参数；
	- 开始编译：用上一步得到的参数初始化 Compiler 对象，加载所有配置的插件，执行对象的 run 方法开始执行编译；
	- 确定入口：根据配置中的 entry 找出所有的入口文件；
	- 编译模块：从入口文件出发，调用所有配置的 Loader 对模块进行翻译，再找出该模块依赖的模块，再递归本步骤直到所有入口依赖的文件都经过了本步骤的处理；
	- 完成模块编译：在经过第4步使用 Loader 翻译完所有模块后，得到了每个模块被翻译后的最终内容以及它们之间的依赖关系；
	- 输出资源：根据入口和模块之间的依赖关系，组装成一个个包含多个模块的 Chunk，再把每个 Chunk 转换成一个单独的文件加入到输出列表，这步是可以修改输出内容的最后机会；
	- 输出完成：在确定好输出内容后，根据配置确定输出的路径和文件名，把文件内容写入到文件系统。
	- 在以上过程中，Webpack 会在特定的时间点广播出特定的事件，插件在监听到感兴趣的事件后会执行特定的逻辑，并且插件可以调用 Webpack 提供的 API 改变 Webpack 的运行结果。
1. babel转译过程：parsing、transforming、generating
	- ES6代码输入
	- babylon 进行解析得到 AST
	- plugin 用 babel-traverse 对 AST 树进行遍历转译,得到新的AST树
	- 用 babel-generator 通过 AST 树生成 ES5 代码


---
### part-6:框架（vue、react）

1. [vue 的响应式原理](./part-6/vue.md)
1. [Vue的通信形式](./part-6/vue-data.md)
1. React 的运行时
1. [vue 中的 computed、watch](./part-6/computed-watch.md)
1. [vue和react的区别](./part-6/vue-react.md)
1. [react中hooks原理](./part-6/vue-react.md)
	- 单向链表通过next把hooks串联起来
	- memoizedState存在fiber node上，组件之间不会相互影响
	- useState和useReducer中通过dispatchAction调度更新任务
1. vue3 的 类似 hooks 的原理是怎么样的
1. React 中的 controlled component 和 uncontrolled component 区别
1. react-router 内部实现机制

---
### part-7:node及node框架

1. [koa的洋葱模型实现](./part-7/KOA.md)
1. express 框架的核心特性
	- 可以设置中间件来响应 HTTP 请求
	- 定义了路由表用于执行不同的 HTTP 请求动作
	- 可以通过向模板传递参数来动态渲染 HTML页面
1. nodejs 的 eventEmitter 的实现
1. Node 异步单线程原理
1. 为什么说node适合io密集型(./part-7/IO.md)
1. Node Node 如何多进程
1. 如何更好的处理线上的日志
	- 日志分级输出，可以分业务日志错误日志等
	- 可以把日志交给spring管理，定期扫描配置文件达到无需重启的目的，定位到原因就可以把级别调回去
	- 把日志放到WEB目录，通过权限限制外网直接访问，达到浏览器就可以查看日志

---



### part-8:前端优化

1. [缓存](./part-8/Cace.md)
2. [前端性能优化](./part-8/project.md)
- 
---


### part-9:算法

1. [时间复杂度、空间复杂度](./part-9/Complexity.md)
1. [数组排序算法](./part-9/sort.md)
1. [数组去重](./part-9/duplication.md)
1. [二叉树遍历](./part-9/TreeNode.md)


---

### part-10:浏览器相关
1. [同源策略](./part-10/Same-Origin.md)
1. [Cookie共享](./part-10/Cook.md)
1. [URL到页面加载完成](./part-10/URL-browser.md)



### part-11:编译

1. [vue转小程序](./part-10/miniprogram.md)

设计模式
JSONP获得回调值



### part-12:正则

1. [常用正则](./part-10/Often.md)



hooks和class Component的区别



面试遇到的问题：
1. http协议的迭代和每个版本的问题
1. 模块化的演进就每个方案的问题
1. 0.5px
1. 文本一行居中两个左对齐
1. qiankun.js样式隔离及优化
1. Object.is() 方法判断两个值是否为同一个值。


vue源码好处
new Vue()做了什么
import require区别 、 es module 和 commonjs 的区别
webpack不同版本差异

emit实现



准备问题：

应用层协议：SMTP、Telnet区别
302
304


ui打包框选择：文件结构、打包配置、文档
glup：方便静态语言分析，tree-shareking


快排
https://www.ruanyifeng.com/blog/2011/04/quicksort_in_javascript.html

二叉树后续遍历

docker的基本知识
UDP协议和其应用场景
flex: 0 1 auto; 是什么意思？
说说redux 的理念；
在项目中如何做性能优化的？
react 16 生命周期有什么改变？
详细的介绍一下 getDerivedStateFromProps




css modules 的原理
webpack 如何实现动态加载
react 里有动态加载的 api 吗？ react 里如何做动态加载？ 动态加载的原理是什么？
写一个 promise 重试函数，可以设置时间间隔和次数
实现一个 redux。实现 createStore 的功能，关键点发布订阅的功能，以及取消订阅的功能
用 ts 实现一个 redux


dva 和 redux 的区别
（1）dva
①定位：dva 首先是一个基于 redux 和 redux-saga 的数据流方案，然后为了简化开发体验，dva 还额外内置了 react-router 和 fetch，所以也可以理解为一个轻量级的应用框架。dva = React-Router + Redux + Redux-saga；
②核心：
•State：一个对象，保存整个应用状态；
•View：React 组件构成的视图层；
•Action：一个对象，描述事件
•connect 方法：一个函数，绑定 State 到 View
•dispatch 方法：一个函数，发送 Action 到 State
③model：dva 提供 app.model 这个对象，所有的应用逻辑都定义在它上面。
④model内容：
•namespace：model的命名空间；整个应用的 State，由多个小的 Model 的 State 以 namespace 为 key 合成；
•state：该命名空间下的数据池；
•effects：副作用处理函数；
•reducers：等同于 redux 里的 reducer，接收 action，同步更新 state；
•subscriptions：订阅信息


（2）redux   redux 的原理
①定位：它是将flux和函数式编程思想结合在一起形成的架构；
②思想：视图与状态是一一对应的；所有的状态，都保存在一个对象里面；
③API：
•store：就是一个数据池，一个应用只有一个；
•state：一个 State 对应一个 View。只要 State 相同，View 就相同。
•action：State 的变化，会导致 View 的变化。但是，用户接触不到 State，只能接触到 View。所以，State 的变化必须是 View 导致的。Action 就是 View 发出的通知，表示 State 应该要发生变化了。Action 是一个对象。其中的type属性是必须的，表示 Action 的名称。其他属性可以自由设置。
•dispatch：它是view发出action的唯一方法；
•reducer：view发出action后，state要发生变化，reducer就是改变state的处理层，它接收action和state，通过处理action来返回新的state；
•subscribe：监听。监听state，state变化view随之改变；




ESM
UI和框架、项目工程化(打包)选择的差别



写 new 的执行过程
写一个处理加法可能产生精度的函数，比如 0.1 + 0.2 = 0.3： 得到输入数字的精度

Cookie和Session有什么区别？ Session在服务端



3、说一下浏览器缓存；
（1）浏览器缓存分为强缓存和协商缓存，强缓存会直接从浏览器里面拿数据，协商缓存会先访问服务器看缓存是否过期，再决定是否从浏览器里面拿数据。
（2）控制强缓存的字段有：Expires和Cache-Control，Expires 和 Cache-Control。
（3）控制协商缓存的字段是：Last-Modified / If-Modified-Since 和 Etag / If-None-Match，其中 Etag / If-None-Match的优先级比Last-Modified / If-Modified-Since高。

对于 CORS ，Get 和 POST 有区别吗？
怎么防止 csrf 和 xss？
（1）xss：恶意攻击者往 Web 页面里插入恶意 Script 代码，当用户浏览该页之时，嵌入其中 Web 里面的 Script 代码会被执行，从而达到恶意攻击用户的目的。
（2）csrf：CSRF 攻击是攻击者借助受害者的 Cookie 骗取服务器的信任，可以在受害者毫不知情的情况下以受害者名义伪造请求发送给受攻击服务器，从而在并未授权的情况下执行在权限保护之下的操作





容灾
为什么用 mysql
中间件的理解
async 和 defer 的不同
fastclick 解决点击穿透的原理
for...in 迭代和 for...of 有什么区别
说一下你对 generator 的了解？

React Native 的运行机制
Cordova PhoneGap 的运行机制



lazyloader 实现

常考算法题：
- 最长公共前缀
- 二叉树遍历：前中后续遍历（递归非递归）、按层遍历、路径和
- 排序：快排
- 岛屿
- 36进制加法

常见笔试题：
1. 手写深浅拷贝
1. 用原生 JS 模拟一个 bind
1. 用原生 JS 实现promise、promise-all 
1. 发布订阅系统：on、emit、off
1. 手写函数防抖和节流
1. 使用 es5 实现 es6 的 class
1. 实现一个sleep函数
```javascript
async function sleep(time){
 // 这里是实现
 return new Promise((res)=>{
   setTimeout(()=>{
     res()
   },time)
 })
}
console.log(1)
await sleep(3000)
console.log(2)
```



diff算法的实现
mysql的索引

portal ？？？（antd modal）
vue中data为什么是函数
实现redux的connect


实现一个带并发限制的异步调度器Scheduler，保证同时运行的任务最多有两个.(

https://www.zhihu.com/question/33629737
https://juejin.cn/post/6844904100195205133


洗牌算法、找出数组中最大的连续子数组和
tcp如何保证安全连接
dns查询过程，使用的协议
浏览器如何构建和渲染页面
vue指令实现




常见手写代码：
- 防抖节流
- promise.all
- 快排
- 二叉树遍历（DFS、BFS）
- 实现 instanceof