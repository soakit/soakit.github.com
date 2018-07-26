---
layout: post
category: "Javascript"
title:  "Javascript原型总结"
tags: [Javascript]
---

```javascript
function Foo() {}
Object.prototype.name = 'My Object';
Foo.prototype.name = 'Bar';
var obj = new Object();
var foo = new Foo();
console.log(obj.name); // 输出 My Object
console.log(foo.name); // 输出 Bar
console.log(foo.__proto__.name); // 输出 Bar
console.log(foo.__proto__.__proto__.name); // 输出 My Object
console.log(foo.__proto__.constructor.prototype.name); // 输出 Bar
```

## 图示
<img src="https://static.panoramio.com.storage.googleapis.com/photos/medium/122612856.jpg">

## 总结
1. Object.prototype.\_\_proto\_\_ => null
2. `类/对象的原型对象`的`__proto__属性`指向其`父类的原型对象`  <br/>
   `类/对象的原型对象`的`constructor属性`指向`类/对象`本身
3. `类/对象`的`__proto__属性`指向`Function.prototype`  <br/>
   `类/对象`的`prototype属性`指向其`原型对象`
4. `类/对象的实例`的`__proto__属性`指向`类/对象的原型`


