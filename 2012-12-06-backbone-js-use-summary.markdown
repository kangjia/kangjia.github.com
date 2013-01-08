---
comments: true
date: 2012-12-06 18:14:44
layout: post
slug: backbone-js-use-summary
title: backbone.js使用小结
wordpress_id: 303
categories:
- tech
tags:
- backbone
- javascript
---

# BackBone.js


BackBone.js 继承了undercore的集合、数组辅助方法；继承events对象，支持自定义事件和事件命名空间；支持自定义选择器；支持自定义模板引擎的一个MVC框架。

提供了如下三个对象：



	
  * Router 负责监听URL变化，是app入口，作有状态的controller

	
  * View 负责渲染，监听/处理浏览器事件；对外提供渲染行为/事件行为接口

	
  * Model/Collection 负责处理模型数据和后端数据交互，对外提供数据处理API

	
  * 调用顺序:
`R->V->M`
`R->V R->M`




## Router





	
  * 属性

	
    * routes




	
  * 方法

	
    * initialize

	
    * _事件方法_







## View





	
  * 属性

	
    * el

	
    * events


`click .abc : funName`

	
  * 方法

	
    * initialize

	
    * render

	
    * _事件方法_







## Model





	
  * 属性

	
    * urlRoot




	
  * 方法

	
    * initialize

	
    * get

	
    * set

	
    * save

	
    * destory

	
    * fetch

	
    * parse

	
    * _事件方法_







## Collection





	
  * 属性

	
    * model

	
    * url




	
  * 方法

	
    * initialize

	
    * fetch

	
    * get

	
    * _事件方法_







## 其他




###### bind 太弱了，只有bind , unbind , trigger 。 小心循环绑定事件。




###### 用户操作是放在view的events里处理，还是放在router里的routes处理比较迷惑。



    
    目前是需要记录状态的都丢到routes里处理了。 




###### 调用流程是在R里生成V和M的实例，然后调用？还是直接调用V的实例，在V的构造里去生成M的实例？




###### 不同的M或者V之间调用缺少消息中间层，怎么处理才能方便模块加载卸载？



    
    目前是直接通过一个message对象来处理，有点丑陋。 
