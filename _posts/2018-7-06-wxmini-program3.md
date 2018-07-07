---
toc: true
title:  "微信小程序快速入门 (3--WXML 之语法)"
tag: 
  - 微信小程序入门
---

> 小程序页面并不需要用 src 来引入外部 css 文件，在于小程序的文件结构让一个页面所需的 wxss wxml js json 四种资源都在同一文件夹下，程序在编译的时候会自动查找这几个资源文件！

> WXML 是（WeiXin Markup Language）框架设计的一套标签语言，结合组件、WXS 和事件系统，可以构建出页面结构！
> 1. WXML 标签是严格闭合的
> 2. 属性名是大小写敏感的

### 微信小程序框架--基本构成

1. WXML
2. WXSS
3. wxs 是 wxml 能力增强的一种脚本语言，可以把请求到的数据进行 filter 或者计算处理，帮助 WXML 快速构建内容结构
4. JavaScript

### WXML 语言--四个特性
1. 数据绑定 （变量加双括号的方式绑定、三元表达式绑定、字符串运算绑定、组合式绑定、扩展运算符绑定等等！）
2. 列表渲染
3. 条件渲染
4. 模版引用

### 小程序标签--六种属性
1. id   组件的唯一标识--代表标签在整个页面的唯一性
2. class  组件的样式类--对应 WXSS 中定义的样式类
3. style  组件的内联样式--可以动态设置的内联样式
4. hidden 可以控制组件的显示或隐藏--所有组件默认 hidden="false"
5. data-* 自定义属性 
6. bind* / catch*  组件的事件绑定


### 小程序的列表渲染

```html
<!-- goods.wxml -->
<view>
  <block wx:for="｛｛items｝｝" wx:for-item="item" wx:key="index">
      <view>｛｛index｝｝:｛｛item.name｝｝</view>
  </block>
</view>

<!-- goods.js -->
Page({
  data: [
    {name: "商品A"},
    {name: "商品B"},
    {name: "商品C"},
    {name: "商品D"}
  ]
})
```

### 小程序条件渲染

```html
<!-- whatfood.wxml -->
<view>今天吃什么？</view>

<view wx:if="｛｛condition===1｝｝">
饺子
<view>

<view wx:elif="｛｛condition===2｝｝">
米饭
<view>

<view wx:else>
面食
<view>

<!-- whatfood.js -->
Page({
  data: {
    condition: Math.floor(Math.random()*3+1)
  }
})
```
> hidden 和 条件渲染的区别？？ hidden 有初始化消耗（切换时改变css的display属性）----而条件渲染有切换消耗（切换时可能会销毁或新建DOM）

### WXML特性之模板及引用

```html
<!-- index.wxml -->
<template name="tempItem">
    <view>
        <view>收件人：｛｛name｝｝</view>
        <view>联系方式：｛｛phone｝｝</view>
        <view>地址： ｛｛address｝｝</view>
    </view>
</template>

<!-- show.wxml -->
<template is="tempItem" data="｛｛...item｝｝"></template>

<!-- index.js -->
Page({
  data: {
    item: {
      name: {
        name: "张三",
        phone: "13255559999",
        address: "中国"
      }
    }
  }
})
```

### 引用文件之 include 和 import

```html
<!-- index.wxml -->
<import src='a.wxml'></import>
<template is='a'></template>

<!-- a.wxml -->
<view>Hello, world</view>
<template name='a'>
    Hello, world！
</template>
<!-- index.wxml会输出 Hello, world！ -->
<!-- import 引入模板文件后，只能渲染对应模板的内容 -->

```
import 还有一个作用域的概念
```html
<!-- index.wxml -->
<import src='a.wxml'></import>
<template is='a'></template>

<!-- a.wxml -->
<import src='b.wxml'></import>
<template name='a'>
    This is a.wxml
</template>
<template is="b"></template>

<!-- b.wxml -->
<template name="b">
    This is b.wxml
</template>
```
> 上面这段代码会输出 This is a.wxml，这证明了 WXML 中的模板不会循环引用

### include 和 import 的区别

```html
<!-- index.wxml -->
<include src='a.wxml'></include>
<template is='a'></template>

<!-- a.wxml -->
<template name='a'>
    <view>This is a.wxml</view>
</template>
<view>Hello, world!</view>
<!-- index.wxml会输出 Hello, world! -->
```



