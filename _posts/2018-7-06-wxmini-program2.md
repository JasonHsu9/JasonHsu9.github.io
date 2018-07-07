---
toc: true
title:  "微信小程序快速入门 (2--开发环境搭建)"
tag: 
  - 微信小程序入门
---
> 直接下载 微信 Web 开发者工具即可动手开发，也可使用其它编辑器编辑文件，在微信 Web 开发者工具中编译预览即可
> 微信 Web 开发者工具界面包括四个部分
> 1. 模拟器界面
> 2. 编辑器界面
> 3. 调试界面
> 4. 顶部工具栏

## 传统的 Web 页面结构

```
//js文件为页面逻辑（英雄技能）文件
//css文件为页面样式（英雄皮肤）文件
//wxml文件为页面骨架（英雄骨胳）文件
//json文件为配置（英雄天赋-出场就有的）文件
//project.config.json 文件保存了我们对开发者工具的一些配置信息，切换电脑时，只要加载这个文件，就可以恢复开发者工具的界面设置!
```
可以看出，小程序开发和传统的 Web 开发是类似的！**页面层级不超过5级**



## 手动创建纯净的 Hello 小程序

```js
//在不使用小程序提供的快速启动模版的情况下，如何让最简单的 Hello 程序直接跑起来？只需要如下几步！！
//1 创建小程序全局所必须的 app.js app.json app.wxss 三个文件
//2 创建入口文件夹 /pages/welcome
//3 在步骤2的 welcome 目录下创建基本页面所需的三个文件 welcome.js welcome.wxml welcome.wxss

//目录结构创建好后，直接在 app.json 中配置入口文件，在 /pages/welcome/welcome.wxml 文件中编写代码。Ctrl + s 保存即可自动编译并在模拟器预览! 下面是源代码
```

app.json 中

```json
{
  "pages": [
    "pages/welcome/welcome"
  ]
}
```

pages/welcome/welcome.wxml 中

```html
<!-- pages/welcome/welcome.wxml中 -->
<!-- wxml文件是项目骨架文件 -->
<!-- 小程序的view相当于html中的div，它起到容器的作用 -->
<!-- 以后可以让设计师以iPhone6的宽度750px为标准，出设计图，然后我们在程序中就可以直接使用设计师给出的宽度，并且以rpx为单位 -->
<view>
    <text>
Hello Weixin
    </text>
</view>
<!-- 至此 Hello 小程序即可成功运行了 -->

```

## 小程序有五个版本
1. 预览版本 
2. 体验版本（后台设置）
3. 开发版本（后台设置）
4. 审核版本
5. 线上版本

