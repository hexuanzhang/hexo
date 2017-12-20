---
title: tslint 错误提示归纳
date: 2017-12-13 18:48:55
updated_at: 2017-12-14 14:40:45
tags: ['tslint']
categories: ['tslint']
---

## 组件选择器错误
### 错误信息

```
TSLint: The selector of the component "xxx" should have prefix "app" (https://goo.gl/cix8BY)(component-selector)
```
### 解决方法    
>   修改 `tslint.json` 中 `component-selector` 属性值为 false
    
```
"component-selector": [false, "element", "app", "kebab-case"],
```

## 注释错误
### 错误信息

```
TSLint: comment must start with a space (comment-format)
```

### 解决方法
>   修改 `tslint.json` 中 `comment-format` 属性值为 false

```
"comment-format": [true,  "check-space"],  
```

### 扩展
>   `comment-format` 属性提供三个参数
>   *   `check-space`：要求所有单行注释必须以空格开头 `// comment`
>   *   `check-lowercase`：要求注释的第一个非空白字符必须为小写
>   *   `check-uppercase`：要求注释的第一个非空白字符必须是大写

```
"comment-format": [true, "check-space", "check-uppercase"]
```
```
"comment-format": [true, "check-lowercase", {"ignore-words": ["TODO", "HACK"]}]
```
```
"comment-format": [true, "check-lowercase", {"ignore-pattern": "STD\\w{2,3}\\b"}]
```

## 变量声明错误
### 错误信息

```
TSLint: Identifier 'errMsg' is never reassigned; use 'const' instead of 'let'. (prefer-const)
```

### 解决方法
>   修改 `tslint.json` 中 `prefer-const` 属性值为 false

```
"prefer-const": false
```

## 推断类型错误
### 错误信息

```
Type string trivially inferred from a string literal, remove type annotation (no-inferrable-types)
```

### 解决方法
>   ts 不允许对初始化为数字、字符串或布尔值的变量或参数进行显式类型声明
>   添加 `tslint.json` 中 `no-inferrable-types` 属性值 `ignore-properties`

```
"no-inferrable-types": [true, "ignore-params", "ignore-properties"]
```

### 扩展
>   `no-inferrable-types` 属性提供两个参数
>   *   `ignore-params`：允许为函数参数指定不可推出的类型注释
>   *   `ignore-properties`：允许为类属性指定不可推出的类型注释

## 参考
*   [TSLint core rules](https://palantir.github.io/tslint/rules/)
*   [rules](https://eslint.org/docs/rules/)


