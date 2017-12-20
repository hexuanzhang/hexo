---
title: 《CSS 揭秘笔记》
date: 2017-11-14 21:46:57
updated_at: 2017-11-24 22:22:10
tags: [css]
categories: [css]
---

## 背景与边框
### 半透明边框
#### 问题
>   通常情况下，背景（色或图片）会延伸至元素边框外沿（但在边框下面），这种情况会导致边框和背景产生重叠，半透明边框呈现出来的是背景，无法实现半透明边框

#### 解决方案
>   通过 `background-clip` 属性调整元素背景延伸范围

[Demo](https://codepen.io/zhanghx/pen/YExKYK)

```
background-clip: [border-box] |[padding-box] | [content-box];

hsla(<色相>, <饱和度>, <明度>, <透明度>)
色相：0~360
饱和度：0%~1000% 
明度： 0%（黑色）~100%（白色）
透明度：0~1
```

```
border: 10px solid hsla(175, 100%, 60%, .5);
background-clip: padding-box;
background: #03a9f4;  
```

## 多重边框
>   实现多重边框

### box-shadow 方案

[Demo](https://codepen.io/zhanghx/pen/dZzxpR)

```
box-shadow:none|| inset && [<x-offset> <y-offset> <blur-radius> <spread-radius> <color>];
```

```

div {
	width: 100px;
	height: 60px;
	margin: 25px;
	background: yellowgreen;
	box-shadow: 0 0 0 10px #655,
            0 0 0 15px deeppink,
            0 2px 5px 15px rgba(0,0,0,.6);
}
```

### outline 方案

[Demo](https://codepen.io/zhanghx/pen/aVyeLp)

```
outline：outline-width  || outline-style ||outline-color
```

```
border:10px solid #655;
outline: 5px solid deeppink;
```

### 对比
*   `box-shadow` 方案可以实现多层边框，但只能模拟实线边框
*   `outline` 方案只能实现两层边框，但边框的样式可以与 `border` 一样灵活，也可以通过 `outline-offset` 属性调整与边框的距离；另外，如果边框为圆角时，`outline` 无法贴合圆角

## 灵活的背景定位
>   背景图片定位在大小不固定的容器右下角，距底部和右边 20px

### background 方案
[Demo](https://codepen.io/zhanghx/pen/LOrmXM)

```
background-position: <percentage> || <length> || [left | center| right] [, top | center | bottom]
background-origin: padding-box || border-box || content-box
```

```
background: url(code-pirate.svg) no-repeat bottom right #58a;
background-position: right 20px bottom 10px;

padding: 0 10px 20px 0;
background: url(code-pirate.svg) no-repeat bottom right #58a;
background-origin: content-box;
```

### calc 方案
[Demo](https://codepen.io/zhanghx/pen/GOGdxV)

```
calc: (四则运算)
```

```
background: url(code-pirate.svg) no-repeat bottom right #58a;
background-position: calc(100% - 20px) calc(100% - 10px);
```

