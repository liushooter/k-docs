# Hybrid 技术调研

## 移动 App 开发技术分类

### Web App 

[介绍](http://www.cocoachina.com/applenews/devnews/2012/0709/4428_2.html)

* 成本低，快速开发
* 响应式设计
* 浏览器运行很多手机特性无法访问。例如联系人，推送等
* single page app
* 销售渠道限制于浏览器

### Native App 

[介绍](http://www.cocoachina.com/applenews/devnews/2012/0709/4428.html)

* 学习成本高，开发成本高，开发效率低
* 不同平台一道坎

### Hybrid App 

[介绍](http://www.cocoachina.com/applenews/devnews/2012/0709/4428_3.html)

## Hybrid App 优点 

* 兼具 Native App 良好用户体验的优势和 Web App 跨平台开发的优势
* 开发成本和难度比 Native App 小
* 使得开发和日常维护过程变得集中式、更简短、更经济高效
* 既可以通过 Native 分发渠道推广产品，也可同时在微信，百度轻，UC等移动平台推广


## 现状

* 国外的 Facebook，App Store
* 国内的百度搜索，淘宝客户端 Android 版。其中百度封装的不是 WebView 而是自己的浏览内核，体验更像原生客户端，更高效。

## Hybrid 含义

* mobile application: 就是一个移动应用
* both browser-supported language and computer language: 同时使用网页语言和程序语言编写
* avaiable through application distribution platforms: 通过应用商店进行分发
* a target device: 区分目标平台
* install to run: 用户需要安装使用

## Hybrid 类型

* 多 View 混合型
* 单 View 混合型
* Web 主体型

### 多 View 混合型(中)

即 Native View 和 Web View 独立展示，交替出现。例如我们第一版本的安卓 App。

### 单 View 混合型(好)

即在同一个 View 内，同时包括 Native View 和 Web View。互相之间是覆盖（层叠）的关系。

这种 Hybrid App 的开发成本较高，开发难度较大，但是体验较好。

例如百度搜索为代表的单 View 混合型移动应用，既可以实现充分的灵活性，又能实现较好的用户体验。 

### Web 主体型(差)

即移动应用的主体是 Web View，主要以网页语言编写，穿插 Native 功能的 Hybrid App 开发类型。

这种类型开发的移动应用体验相对而言存在缺陷，但整体开发难度大幅降低，并且基本可以实现跨平台。

Web 主体型的移动应用用户体验的好坏，主要取决于底层中间件的交互与跨平台的能力。

国外的 appMobi、PhoneGap 国内的 AppCan 和 Rexsee 都属于 Web 主体型移动应用中间件。其中 Rexsee 不支持跨平台开发。appMobi 和 PhoneGap 除基础的底层能力更多是通过插件（Plugins）扩展的机制实现 Hybrid。而 AppCan 除了插件机制，还提供了大量的单 View 混合型的接口来完善和弥补 Web 主体型 Hybrid App 体验差的问题，接近Native App 的体验。 


## 中间件

App 的 Native 代码部分使用操作系统的 API 来创建嵌入式 HTML 渲染引擎，该引擎在浏览器和设备的 API 之间充当了桥梁。这座桥梁让 Hybrid App 得以充分利用现代设备所提供的全部特性。

App 开发者可以选择编写自己的桥梁，或者充分利用现成的解决方案，比如 PhoneGap。

App 的 Web 部分可能是驻留在服务器上的网页，也可能是一组 HTML、JavaScript、CSS 和媒体文件，封装到 App 代码中，存储在设备本地。

* 放置在服务器上的 HTML 代码让开发者不必经历提交和批准过程——有些App商店要求这个过程，就可以对 App 进行小幅更新。遗憾的是，这个方法摈弃了任何离线可用性，因为设备与网络没有连接时，无法访问设备。
* 把 Web 代码封装到 App 里面可以提高性能和可访问性，但是不允许远程更新。
* 推荐的方案是：结合使用两者。这种系统采用的架构可以把 HTML 资源放置在 Web 服务器上，以获得灵活性，但是又把它们本地缓存在移动设备上，以获得高性能。

根据我们目前的技术实力和业务需求，内部时间人力资源预算，不建议使用中间件，以下是市面主流中间件的对比。

![](http://dl.iteye.com/upload/attachment/0070/0982/8b90b009-6cb5-39a7-bf98-ed497674fb76.jpg)

## 最后选择的架构

* Ember 用于双向绑定，网络请求，视图管理等工作
* Require.js JavaScript 模块化工具，能够帮助你把整体的代码管理的井井有条（这块还没决定好）
* Haml + Sass + Coffee

## 题外话

为毛不用 Angular，为毛不用 jade，为毛不用 BackBone，不用 jQuery Mobile，不用 PhoneGap。。。。

我也不知道为啥不用。可能都是命吧。另外朋友们提到的一些技术，例如 jade ，我是确实不了解。可能在具体的开发中，如果发现特别合适的话，就会果断使用的。另外一些，比如 jQuery Mobile，PhoneGap 和 BackBone 确实是各有缺点，不适合我们目前的需求。并不是它们不好，我相信它们都有自己适用的地方。

## 参考资源

* [Web App或夭折，Hybrid App才是新世界的王](http://www.iteye.com/news/25442)
* [HTML5、Native或Hybrid App开发全接触](http://www.cocoachina.com/applenews/devnews/2012/0709/4428_3.html)
* [Hybrid App开发实战](http://www.infoq.com/cn/articles/hybrid-app-development-combat)

## 延伸阅读

* [Hybrid 架构下的 H5 应用加速方案](http://www.aliued.cn/2014/03/02/hybrid-%E6%9E%B6%E6%9E%84%E4%B8%8B%E7%9A%84-h5-%E5%BA%94%E7%94%A8%E5%8A%A0%E9%80%9F%E6%96%B9%E6%A1%88.html?utm_source=tuicool)
* [停不下来的前端，自动化流程](http://www.alloyteam.com/2014/03/frontend-workflow/?utm_source=tuicool)