---
comments: true
date: 2012-12-03 13:23:10
layout: post
slug: jquery-data-method-bug
title: jQuery data取值小坑
wordpress_id: 290
categories:
- tech
tags:
- jQuery
---

开发中经常需要在DOM上绑定数据，类似于

    
    
       <li class="active" data-id="xxx"></li>
    


然后使用jQuery的data函数去取。

    
    $("li.active").data("id");


但是当data-id的数据为数字组成的字符串，会出现问题，比如"01234"，会变成"1234"
查看了jQuery下源码，如下：

    
    
    function dataAttr( elem, key, data ) {
    	// If nothing was found internally, try to fetch any
    	// data from the HTML5 data-* attribute
    	if ( data === undefined && elem.nodeType === 1 ) {
    
    		var name = "data-" + key.replace( rmultiDash, "-$1" ).toLowerCase();
    
    		data = elem.getAttribute( name );
    
    		if ( typeof data === "string" ) {
    			try {
    				data = data === "true" ? true :
    				data === "false" ? false :
    				data === "null" ? null :
    				jQuery.isNumeric( data ) ? +data :
    					rbrace.test( data ) ? jQuery.parseJSON( data ) :
    					data;
    			} catch( e ) {}
    
    			// Make sure we set the data so it isn't changed later
    			jQuery.data( elem, key, data );
    
    		} else {
    			data = undefined;
    		}
    	}
    
    	return data;
    }
    


jQuery会处理data的值

    
    
    jQuery.isNumeric( data ) ? +data 
    


所以在取uuid之类的值时，尽量使用$(el).atrr("data-id");
