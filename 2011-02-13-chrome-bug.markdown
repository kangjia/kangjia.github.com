---
comments: true
date: 2011-02-13 19:09:15
layout: post
slug: chrome-bug
title: chrome诡异事件之document.write无效
wordpress_id: 98
categories:
- tech
tags:
- chrome
- html
---

**背景**




双联广告位在chrome下，会有第一次加载时右联不出现的情况，经查看，是右联的iframe没撑开导致的，在投放代码增加window.parent.ADManager.setIfrmHeight("dlad_right", 300); 后，依然没撑开。




**投放代码**



    
    
    try{
    	var leftAdContent = ""; //左边图片地址
    	var leftAdLink = "";//左边图片链接
    	var rightAdContent = "";//右边图片地址
    	var rightAdLink = "";//右边图片链接
    	var parentDocument = window.parent.document;
    	var leftAdPanel = parentDocument.getElementById("dlad_left").contentWindow.document;
    	leftAdPanel.body.innerHTML = ['<a href="',leftAdLink,'" target="_blank"><img src="',leftAdContent,'"></img></a>'].join("");
    	window.parent.ADManager.setIfrmHeight("dlad_left", 300);
    	document.write(['<a href="',rightAdLink,'" target="_blank"><img src="',rightAdContent,'"></img></a>'].join(""));
    	window.parent.ADManager.setIfrmHeight("dlad_right", 300); 
    }catch(e){} 
    




通过window.setInterval();增加log




**log代码**



    
    
    var otimer = null;
    try{
    	otimer=window.setInterval("console.log('--'+window.parent.document.getElementById('dlad_right').style.height);"  , 1);
    	var leftAdContent = ""; //左边图片地址
    	var leftAdLink = "";//左边图片链接
    	var rightAdContent = "";//右边图片地址
    	var rightAdLink = "";//右边图片链接
    	var parentDocument = window.parent.document;
    	var leftAdPanel = parentDocument.getElementById("dlad_left").contentWindow.document;
    	leftAdPanel.body.innerHTML = ['<a href="',leftAdLink,'" target="_blank"><img src="',leftAdContent,'"></img></a>'].join("");
    	window.parent.ADManager.setIfrmHeight("dlad_left", 300);
    	document.write(['<a href="',rightAdLink,'" target="_blank"><img src="',rightAdContent,'"></img></a>'].join(""));
    	window.parent.ADManager.setIfrmHeight("dlad_right", 300); 
    	console.log("**"+window.parent.document.getElementById("dlad_right").style.height);
    }catch(e){}        
    	setTimeout(function(){
    		window.clearInterval(otimer);
    	},300);
    




**log**





	
  * **300px

	
  * --300px

	
  * --0px

	
  * --0px




**其他**




如果设置间隔时间大于1 ms，就看不到--300px 这个log了。




该问题在其他浏览器中没有这种情况，解决办法就是延迟设置iframe高度，即setTimeout(function(window.parent.ADManager.setIfrmHeight("dlad_right", 300);){},20);



