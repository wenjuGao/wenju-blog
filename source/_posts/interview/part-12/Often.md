---
title: 常用正则
date: 2021-12-16 09:30:39
tags: 面试
---


## 常用正则

1. 邮箱

```javascript
function isAvailableEmail(sEmail) {
    return /^[A-Za-z\d]+([-_.][A-Za-z\d]+)*@([A-Za-z\d]+[-.])+[A-Za-z\d]{2,5}$/.test(sEmail)
}
```