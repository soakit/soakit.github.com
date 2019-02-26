---
layout: post
category: "Javascript"
title:  "Javascript原型总结"
tags: [Javascript]
---

```javascript
function Foo() {}
Object.prototype.name = 'My Object'
Foo.prototype.name = 'Bar'
var obj = new Object()
var foo = new Foo()
console.log(obj.name) // 输出 My Object
console.log(foo.name) // 输出 Bar
console.log(foo.__proto__.name) // 输出 Bar
console.log(foo.__proto__.__proto__.name) // 输出 My Object
console.log(foo.__proto__.constructor.prototype.name) // 输出 Bar
```

## 图示

<img src="//lh3.googleusercontent.com/sAREhDVv0GRw1g8mJSMPPiJFfKQ2v8NfDLCws7Z-h0NQY7FmRnfnzywAQ00MVnNOFm2uNHDZWj0CAM9Mpw=w1407-h947-rw-no" width="100%">

## 总结

1.  Object.prototype.\_\_proto\_\_ => null
2.  `构造函数的prototype`的`__proto__`指向其`父类的prototype` <br/>
    `构造函数的prototype`的`constructor`指向`构造函数`本身
3.  `构造函数`的`__proto__`指向`Function.prototype`
4.  `构造函数的实例`的`__proto__`指向`构造函数的原型`
