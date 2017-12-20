---
title: location.assign() 和 location.replace() 区别
date: 2017-11-07 20:10:29
updated_at: 2017-11-07 20:10:29
tags: ['location', 'tips']
categories: ['javascript']
---

## 对比
### 相同点
>   `assign` 方法和 `replace` 方法都是用户加载并显示指定 URL 的内容

### 异同点
>   与 `assign` 方法不同的是，调用 `replace` 方法后，当前页面不会保存到会话历史中（`session History`），击回退按钮将不会再跳转到该页面

### Demo
[location.assign()](https://www.impressivewebs.com/demo-files/history-back-js/testpage2.html)
[location.replace()](https://www.impressivewebs.com/demo-files/history-back-js-2/)

### 参考
*   [location.assign() MDN](https://developer.mozilla.org/en-US/docs/Web/API/Location/assign)
*   [location.replcae() MDN](https://developer.mozilla.org/en-US/docs/Web/API/Location/replace)
*   [Difference between location.assign() and location.replace()](https://stackoverflow.com/questions/4505798/difference-between-window-location-assign-and-window-location-replace)


