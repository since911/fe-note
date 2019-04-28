# Contents

* [CSS篇](#CSS篇)
  * [垂直居中](#垂直居中)
  * [什么是BFC](#什么是BFC)
  * [移动端实现1px边框](#移动端实现1px边框)
  * [flex布局](#flex布局)
  * [两栏 三栏布局](#两栏-三栏布局)
  * [CSS3动画](#CSS3动画)
* [JS基础篇](#JS基础篇)
  * [箭头函数和普通函数的区别](#箭头函数和普通函数的区别)
  * [var let const 区别](#var-let-const-区别)
  * [call apply bind](#call-apply-bind)
  * [实现Promise](#实现Promise)
  * [async await原理](#async-await原理)
  * [Proxy和Object.defindproperty](#Proxy和Object.defindproperty)
* [Vue框架篇](#快速入门)
  * [双向绑定原理](#双向绑定原理)
  * [vue-router原理](#vue-router原理)
  * [vuex原理](#vuex原理)
  * [axios原理](#axios原理)
  * [vue组件通信&高阶组件](#vue组件化&高阶组件)
  * [后台管理系统权限控制](#后台管理系统权限控制)
  * [服务端渲染](#服务端渲染)
* [web开发综合篇](#属性配置)
  * [跨域](#跨域方案)
  * [HTTP缓存](#HTTP缓存)
  * [https理解](#https理解)
  * [CDN原理](#CDN原理)
  * [sso机制](#sso机制)
  * [什么是JWT](#什么是JWT)
  * [tcp三次握手，四次挥手](#tcp三次握手，四次挥手)
  * [性能优化](#性能优化)
  * [利用谷歌performance进行网页性能分析](#利用谷歌performance进行网页性能分析)
  * [浏览器端的js事件循环和node的事件循环机制区别](#浏览器端的js事件循环和node的事件循环机制区别)
* [webpack](#webpack)
  * [构建&打包优化](#构建&打包优化)
  * [loader和plugin原理](#loader和plugin原理)
* [小程序](#小程序)
  * [登录和认证](#登录和认证)
  * [uniapp框架](#uniapp框架)
* [git常用操作](#git常用操作)
  * [修改本地账户](#修改本地账户)
  * [常用命令](#常用命令)
  * [项目开发中的分支说明](#项目开发中的分支说明)
* [其他](#其他)
  * [单页面微信公众号ios端签名验证失败](#单页面微信公众号ios签名验证失败)
  * [常见的兼容性问题](#常见的兼容性问题)
  * [服务器方面的知识](#服务器方面的知识)

## CSS篇
### 垂直居中
> - 行内元素，table-cell,flex 单行文本使用line-height
> - 多行文本垂直居中 display:inline-block;vertical-align:middle;
> - 块元素垂直居中，position + margin负值 ,position + translate3d ,flex

## JS基础篇
### 箭头函数和普通函数的区别
> - 箭头函数不可以被当作构造函数
> - 箭头函数没有arguments对象,用rest解构参数（...params）代替
> - 不可以使用yield命令，因此箭头函数不能用作 Generator 函数
> - 普通函数this指向它的调用者,箭头函数this继承它的定义者（在哪个对象定义，就指向当前对象）
> - 非严格模式下，没有找到直接调用者的函数，this指向window
> - 严格模式下，没有直接调用者的函数，this为undefined
> - call,apply,bind可以改变普通函数this指向
```javascript
var obj = {
  fun1 : () => {
    console.log(this)
  },
  fun2 : function(){
    console.log(this)
  }
}
obj.fun1() // window
obj.fun2() // obj
```

### var let const 区别
> - var存在变量提升，只有函数作用域
> - let不存在变量提升，有块级作用域
> - const指向当前变量的内存地址，声明时必须赋值，如果是值类型声明后不可修改，引用类型可修改当前对象的属性，但不可改变当前变量的内存地址（即不可重新赋值）
> - let和const不可以重复声明，存在暂时性死区（只要一进入当前作用域，所要使用的变量就已经存在了，但是不可获取，只有等到声明变量的那一行代码出现，才可以获取和使用该变量）

### call apply bind
> - 箭头函数不可以被当作构造函数
> - 箭头函数没有arguments对象,用rest解构参数（...params）代替
> - 不可以使用yield命令，因此箭头函数不能用作 Generator 函数
> - 普通函数this指向它的调用者,箭头函数this继承它的定义者（在哪个对象定义，就指向当前对象）
> - 非严格模式下，没有找到直接调用者的函数，this指向window
> - 严格模式下，没有直接调用者的函数，this为undefined
> - call,apply,bind可以改变普通函数this指向


### 实现Promise
> - var存在变量提升，只有函数作用域
> - let不存在变量提升，有块级作用域
> - const指向当前变量的内存地址，声明时必须赋值，如果是值类型声明后不可修改，引用类型可修改当前对象的属性，但改变当前变量的内存地址（即不可重新赋值）
> - let和const不可以重复声明，存在暂时性死区（只要一进入当前作用域，所要使用的变量就已经存在了，但是不可获取，只有等到声明变量的那一行代码出现，才可以获取和使用该变量）


## Vue框架篇

## web开发综合篇
### https理解
>- 111

## webpack

## 小程序

## git常用操作