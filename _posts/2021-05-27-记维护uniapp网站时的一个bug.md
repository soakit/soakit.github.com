---
layout: post
category: "小程序"
title: "记维护uniapp网站时的一个bug"
tags: [uniapp, 小程序]
---

【日期】：**2021-05-27**

【问题】：**更改表单选项，发送验证码，输入验证码，提交时选项被还原成默认(Chrome 模拟无法重现，真机必现)。**

【如何发现】：**真机重现时，发现 onShow 的回调多执行了一次。**

【如何修复】：**将本页面的 onShow 改为 onLoad。**

【原因】：**验证码短信弹出时，当前页面失焦，输入验证码时再次聚焦，触发了 onShow 的回调。**

【总结】：**要弄清楚 onShow 和 onLoad 的函数区别和使用场景。**

## uniapp API

**onLoad**: 只加载一次，监听页面加载，其参数为上个页面传递的数据，参数类型为 Object（用于页面传参）

**onShow**: 监听页面显示。页面每次出现在屏幕上都触发，包括从下级页面点返回露出当前页面。

主要区别：

- onLoad 先于 onShow 执行
- onLoad 页面的整个生命周期里，只执行一次，而onShow 页面的整个生命周期里，可执行多次，即每次显示都会执行。
- 获取参数并且只请求一次的事件放在 onLoad 里。
- 当前页面需要即时刷数据的-需要请求多次的事件放在 onShow 里。

## 小程序 API

**onLoad**：页面第一次加载时触发，从跳转页面返回时不能触发，可以传递参数

**onShow**：页面显示或从后台跳回小程序时显示此页面时触发，从跳转页面返回时触发，不能传递参数

**onHide**：页面隐藏，例如使用 [wx.navigateTo](https://developers.weixin.qq.com/miniprogram/dev/api/route/wx.navigateTo.html) 只是打开新页面 并不关闭原页面

**onUnload**：页面被卸载，例如使用 [wx.navigateTo](https://developers.weixin.qq.com/miniprogram/dev/api/route/wx.navigateTo.html) 重定向一个页面 原页面已经关闭
