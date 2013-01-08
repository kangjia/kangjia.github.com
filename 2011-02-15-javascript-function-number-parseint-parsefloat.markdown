---
comments: true
date: 2011-02-15 00:40:22
layout: post
slug: javascript-function-number-parseint-parsefloat
title: 学习JavaScript之Number、parseInt、parseFloat
wordpress_id: 111
categories:
- tech
tags:
- javascript
---

**Number()**




Number函数可以转换任何数据类型，尝试转换整个value；





	
  * Boolean值：true-->1，false-->0；

	
  * null值：0；

	
  * undefined：NaN；

	
  * 字符串：
		
			
    * 只有数字：十进制数值，去除前导0

			
    * ""空字符串：0

			
    * 有效浮点数：浮点数值，去除前导0

			
    * 有效16进制（0x1F）：16进制数值

			
    * 其他字符串：NaN

		
	

	
  * 数值：根据0、0x开头转换有效数值，去除前导0



    
     
    	console.log(Number(true));				 //1	
    	console.log(Number(null));				//0
    	console.log(Number(undefined));			//NaN
    	console.log(Number("000012"));		        //12
    	console.log(Number(000012));				//10
    	//注意上两个去除前导0和进制问题。
    	console.log(Number(""));			                //0
    	console.log(Number("00.32"));			        //0.32				
    	console.log(Number("17fuck world")); 		//NaN
    	console.log(Number(true));				//1			
    




**parseInt()**




pareseInt函数会转换字符串成整数，规则如下





	
  * 非0数字或者负号开始字符串：转换有效十进制整数

	
  * 0开始数字:转换有效8进制整数

	
  * 0x开始数字:转换有效16进制整数

	
  * 其他开始字符串:NaN



    
     
    	console.log(parseInt("-3.4abc"));		//-3	
    	console.log(parseInt("023.23"));		//19
    	console.log(parseInt("0x23.23"));		//35
    	console.log(parseInt("ab33"));		        //NaN
    




parseInt(arg1,arg2)使用时注意使用第二个参数，表示进制




BTW：arg1不是字符串时必须注意是有效数值！undefined、null、Boolean都为NaN



    
     
    	console.log(parseInt(101,2));				//5
    	console.log(parseInt(101,8));				//65
    	console.log(parseInt(101,10));				//101
    	console.log(parseInt(101,16));				//257
    	//切记第二个参数哦，jinpu大神面试我的题目哇～～
    




**parseFloat()**




parseFloat函数是转换字符串成浮点数函数，特性两个：





	
  * parseFloat(str)解析是从str的index=0开始解析有效浮点数，遇到非有效浮点数停止解析

	
  * 忽略前导0



    
     
    	console.log(parseFloat("23.32.ab"));		        //23.32
    	console.log(parseFloat("0023.32.ab"));	        //23.32
    	console.log(parseFloat(23.32));				//23.32
    
