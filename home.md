---
title: 首页
description: 
published: true
date: 2023-11-15T13:35:02.900Z
tags: 
editor: markdown
dateCreated: 2023-10-24T08:47:15.075Z
---

# 前端常用框架 React
这是React官网 [React](https://react.dev/)

直到2022年 React在前端占比依然是第一 [来源](https://2022.stateofjs.com/en-US/libraries/front-end-frameworks/)

React使用JSX语法 当然也可以使用TSX
JSX和JS在很多地方几乎没有区别 或者说 任何一个JS代码都是合法的JSX代码

一般来说 JSX使用Babel解析 [Babel](https://babeljs.io/)
Babel将JSX代码转换成JS代码 并交给浏览器执行
很明显 浏览只认识Javascript 不认识其他的 需要使用编译器编译

例如 这段代码
```jsx
const button = <MyButton color="blue" shadowSize={2}>
  Click Me
</MyButton>
```
使用Babel编译后长这样: [React.createElement()](https://react.dev/reference/react/createElement)
```js
React.createElement(
  MyButton,
  {color: 'blue', shadowSize: 2},
  'Click Me'
)
```
事实上 JSX仅仅只是```React.createElement(component, props, ...children)``` 函数的语法糖
可以使用```React.createElement()```自己编写```render()```部分来跳过编译步骤

类似的 Vue里的```<template></template/>```也是```render()```函数的语法糖

什么是语法糖？
> 语法糖（英语：Syntactic sugar）是由英国计算机科学家彼得·兰丁发明的一个术语，指计算机语言中添加的某种语法，这种语法对语言的功能没有影响，但是更方便程序员使用。语法糖让程序更加简洁，有更高的可读性。

```ts
let arr: number[] = [1, 2, 3, 4];
for (let i = 0; i < arr.length; i++) {
    arr[i] = arr[i] * 2;
}
let sum = 0;
for (let i = 0; i < arr.length; i++) {
    sum = sum + arr[i];
}
console.log(sum);
```
使用语法糖之后 我们可以这样写
```ts
let arr: number[] = [1, 2, 3, 4];
arr = arr.map((item) => item * 2);
let sum: number = arr.reduce((prev, curr) => prev + curr);
console.log(sum);
```
甚至 我们可以这样写
```ts
console.log([1, 2, 3, 4].map((item) => item * 2).reduce((prev, curr) => prev + curr))
```
这是[Java的语法糖](https://zhuanlan.zhihu.com/p/78454816)
我们知道 在C++中 string类型是不能用作swtich-case里的 但是很多有语法糖的语言都支持
![有语法糖的switch-case in string](https://pic1.zhimg.com/80/v2-660a7c84fe165c2cb7b48b62af61d2b4_720w.webp)
![desugar()过的代码](https://pic1.zhimg.com/80/v2-9e8aa7a0cb323b5c8483b188fafcab40_720w.webp)
但是Javascript好像原生就支持 那就不算语法糖了

这是一个我写的比较复杂的React项目 可以来看一下 [voanews-frontend](https://github.com/JuTemp/voanews-frontend) [local](/Documents/Langs/React/voanews-router/src/Components/Desc/Desc.tsx)
其中这个代码是比较复杂的 可以看一下语法结构 [Desc.tsx](https://github.com/JuTemp/voanews-frontend/blob/main/src/Components/Desc/Desc.tsx)

```jsx
import React, { useEffect, useState } from 'react';
import './style.module.css'
...

export const Desc: React.FC = () => {

  const [Content, setContent] = useState<[string, string][]>([])
  ...

  useEffect(() => {
    ...
  }, [dependency])

  const playOrPause = () => {
    ...
  }

  return (
    <>
      <section className={style.container}>
      </section>
    </>
  )
}
```
```<Fragment/>``` 可以[简写](https://react.dev/reference/react/Fragment)为```<></>```
这就是React项目主要的结构

另外 如果想实现更复杂的功能 可能会用到
[React Router](https://reactrouter.com/) 这是前端路由管理  
[Redux](https://redux.js.org/) 这是负责管理更复杂的数据结构用的  
[Ant Design](https://ant.design/) 这是前端UI库

例如 [正版化重构开发环境](http://dev.soft.online.njtech.edu.cn/)就是用的React Router
