---
layout: post
category: "Javascript"
title:  "自定义实现lodash的template方法"
tags: [Javascript]
---

```javascript
function template(strArr, ...keys) {
  return function(...values) {
    var dict = values[values.length - 1] || {}
    var result = [strArr[0]]
    keys.forEach(function(key, i) {
      var value = Number.isInteger(key) ? values[key] : dict[key]
      result.push(value, strArr[i + 1])
    })
    return result.join('')
  }
}
```

### 示例

```javascript
var str = `hello ${'data'}!`
var compiled1 = template(str.split('data'), 'data')({ data: 'world' })
console.log(compiled1) // hello world!

var str2 = `${0}${1}${0}!`
var compiled2 = template(str2.split(/\d/), 0, 1, 0)('S', 'O')
console.log(compiled2) // SOS!
```
