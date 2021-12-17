---
title: es6常用API 
date: 2021-12-16 09:30:39
tags: 面试
---



```javascript
class EventEmiter {
    constructor() {
        this.events = {}
    }
    emit(event, ...args) {
        this.events[event].forEach(fn => {
            fn.apply(this, args)
        })
    }
    on(event, fn) {
        if (this.events[event]) {
            this.events[event].push(fn)
        } else {
            this.events[event] = [fn]
        }
    }
    remove(event) {
        delete this.events[event]
    }
}

const eventHub = new EventEmiter()

eventHub.on('test', data => {
    console.log(data)
})
```