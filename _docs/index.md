---
layout: docs
title: 前言
next_section: quickstart
permalink: /docs/home/
---

webGL可以让我们在canvas上实现3D效果。而three.js是一款webGL框架，由于其易用性被广泛应用。
如果你要学习webGL，抛弃那些复杂的原生接口从这款框架入手是一个不错的选择。

博主目前也在学习three.js，发现相关资料非常稀少，甚至官方的api文档也非常粗糙，很多效果需要自
己慢慢敲代码摸索。所以我翻译了《Learning Three.js: The JavaScript 3D Library for WebGL》这
个教程的目的一是自己总结，二是与大家分享。

## 那么问题就来了，什么是WebGL和Three.js?

随着数月的流逝，我们想一想90年代的浏览器，它只能显示简单的文字和图片；大约在2000左右，浏览器
已经能够显示丰富的多媒体信息了；但是相对与传统的桌面程序来说，它还是有一些不足，例如，很难写出
高质量的三维程序。但是现在，有了WebGL规范，一切都成为可能。越来越多的浏览器开始全方位的支持
WebGL了。使用WebGL原生的API来写3D程序是一件非常痛苦的事情，幸好，有很多同行花业余时间写了一
些WebGL开源框架，其中three.js就是非常优秀的一个，它掩盖了很多麻烦的细节，那么，就让我们一起来
看看，什么是three.js吧.

## Three.js 中的一些概念

在Three.js中，要渲染物体到网页中，我们需要3个组建：场景（scene）、相机（camera）和渲染器（renderer）。有了这三样东西，才能将物体渲染到网页中去。

记住关建语句：有了这三样东西，我们才能够使用相机将场景渲染到网页上去。

<div class="note">
  <h5>Scene 场景</h5>
  <p>在Threejs中场景就只有一种，用THREE.Scene来表示，要构件一个场景也很简单，只要new一个对象就可以了，代码如下：

     <span class="command">
     var scene = new THREE.Scene();
     </span>

     场景是所有物体的容器，如果要显示一个苹果，就需要将苹果对象加入场景中。</p>
</div>

<div class="note">
  <h5>Camera 相机</h5>
  <p>另一个组建是相机，相机决定了场景中那个角度的景色会显示出来。相机就像人的眼睛一样，人站在不同位置，抬头或者低头
  都能够看到不同的景色。

     场景只有一种，但是相机却又很多种。和现实中一样，不同的相机确定了呈相的各个方面。比如有的相机适合人像，有的相机
     适合风景，专业的摄影师根据实际用途不一样，选择不同的相机。对程序员来说，只要设置不同的相机参数，就能够让相机产
     生不一样的效果。

     在Threejs中有多种相机，这里介绍两种，它们是：

     透视相机（THREE.PerspectiveCamera）、这里我们使用一个透视相机，透视相机的参数很多，这里先不详细讲解。后面
     关于相机的那一章，我们会花大力气来讲。定义一个相机的代码如下所示：
  </p>
</div>

```bash
var camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
```

<div class="note">
  <h5>Renderer 渲染器</h5>
  <p>最后一步就是设置渲染器，渲染器决定了渲染的结果应该画在页面的什么元素上面，并且以怎样的方式来绘制。这里我们定义
  了一个WebRenderer渲染器，代码如下所示：

  var renderer = new THREE.WebGLRenderer();
  renderer.setSize(window.innerWidth, window.innerHeight);
  document.body.appendChild(renderer.domElement);
  </p>
</div>


本书的源码有些错误，我已经修改并push到github上，读者可以 [点击这里](https://github.com/leiguorui/learning-threejs) 获取代码。
