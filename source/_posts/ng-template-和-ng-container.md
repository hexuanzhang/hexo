---
title: ng-template 和 ng-container
date: 2017-12-22 20:03:38
updated_at: 2017-12-22 20:03:38
tags: ['angular']
categories: ['angular']
---

## ng-template
>   `ng-template`  是 Angular 结构型指令中的一种，用于定义模板渲染 HTML。
>
>   **定义的模板不会直接显示出来，需要通过其他结构型指令（如** `ng-if`**）或** `template-ref` **将模块内容渲染到页面中。**
>
>   另外，在渲染页面之前，Angular 会把<ng-template>及其内容替换为注释

```
<div *ngIf="isActive; then trueContent else falseContent"></div>

<ng-template #trueContent>
	<h3>{{isActive}} template</h3>
</ng-template>

<ng-template #falseContent>
	<h3>{{isActive}} template</h3>
</ng-template>
```

![](https://ws3.sinaimg.cn/large/006tKfTcgy1fmpllecj9oj30no0iygow.jpg)

## ng-container
>   `ng-container` 也是Angular 结构型指令中的一种，用于包裹控制内部元素的显示与否。
>
>   `ng-container` 可以直接包裹任何元素，包括文本，但本身不会生成元素标签，也不会影响页面样式和布局。**包裹的内容，如果不通过其他指令控制，会直接渲染到页面中。**
>
>   有些元素标签不允许包含其标签，如 ul 中只能包含 li 标签，select 中只能包含 option 标签，这种情况下可以使用 `ng-container` 指令有效控制标签的显示与否

```
p span { color: red; font-size: 70%; }

<p>
  I turned the corner
  <span *ngIf="hero">
    and saw {{hero.name}}. I waved
  </span>
  and continued on my way.
</p>
```

```
<ul>
    <div *ngFor="let todo of todos">
        <li *ngIf="todo.content !== 'Get milk'">{{ todo.content }}</li>
    </div>
</ul>

<ul>
    <ng-container *ngFor="let todo of todos">
        <li *ngIf="todo.content !== 'Get milk'">{{ todo.content }}</li>
    </ng-container>
</ul>
```

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fmpn2nb3rej30ks0fadh9.jpg)

