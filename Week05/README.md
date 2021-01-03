# 学习笔记

## Proxy

拦截默认操作

```javascript
let obj = {a: 1};
let proxy = new Proxy(obj, {}); // new Proxy(target, handler)
```



Proxy.revocable创建可解绑的proxy对象。

```javascript
let obj = {a: 1};
let {proxy, revoke} = Proxy.revocable(obj, {}); // Proxy.revocable(target, handler)
proxy.a = 2;
revoke();
proxy.a = 3 //TypeError
```



## Reflect

Reflect Api

## CSSOM

存取元素样式、操作样式表、获取元素尺寸。