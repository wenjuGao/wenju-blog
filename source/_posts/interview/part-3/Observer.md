---
title: 模块化的演进
date: 2021-12-16 09:30:39
tags: 面试
---


```javascript
type Listener = (eventName: String, info: unknown) => unknown;

class EventBus {
  listenerMap: Map<string, Listener[]>;
  constructor() {
    this.listenerMap = new Map();
  }

  on(eventName: string, fn: Listener) {
    const { listenerMap } = this;
    if (!listenerMap.has(eventName)) {
      listenerMap.set(eventName, []);
    }

    listenerMap.get(eventName).push(fn);
  }

  emit(eventName: string, info?: unknown) {
    const { listenerMap } = this;
    if (!listenerMap.has(eventName)) {
      return;
    }

    const listeners = listenerMap.get(eventName);
    listeners.forEach(listener => listener(eventName, info));
  }

  off(eventName: string) {
    const { listenerMap } = this;
    if (listenerMap.has(eventName)) {
      listenerMap.delete(eventName);
    }
  }
}
```