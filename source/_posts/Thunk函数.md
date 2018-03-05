---
title: Thunk函数
date: 2018-03-05 16:25:57
tags:
---

## 传值与传名(call by value or call by name)

首先定义一个函数：

```javascript
var x = 1;

function f(m) {
  return m * 2;
}

f(x + 5)
```

传值调用等同于：

```javascript
f(x + 5)

// 传值调用等同于
f(6)

```

传名调用等同于：

```javascript
f(x + 5)

// 传名调用等同于
(x + 5) * 2
```

传值调用与传名调用各有利弊，传值调用简单，传名调用某些场景下面性能更加好

```javascript
// 这个场景下传值调用性能会有损失
function f(a, b) {
  return b;
}

f (x + 1, x)
```

上面的代码中，a参数并未使用到，但是如果传递一个x进去，a参数也被计算了，这个时候，传名调用更加好一点


## JS怎么样进行一个传值调用呢？



