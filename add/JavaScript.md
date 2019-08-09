# JavaScript

一.Javascript组成

JavaScript的实现包括以下3个部分：基本语法+网页+浏览器

ECMAScript(核心)      			描述了JS的语法和基本对象。

文档对象模型 （DOM）   		  处理**网页**内容的方法和接口

浏览器对象模型（BOM）         	  与**浏览器**交互的方法和接口

javascript 有三部分构成，ECMAScript，DOM和BOM，根据宿主（浏览器）的不同，具体的表现形式也不尽相同，ie和其他的浏览器风格迥异,IE 扩展了 BOM，加入了 ActiveXObject 类，可以通过 JavaScript 实例化 ActiveX 对象

 

1. DOM 是 W3C 的标准； [所有浏览器公共遵守的标准]
2. BOM 是 各个浏览器厂商根据 DOM在各自浏览器上的实现;[表现为不同浏览器定义有差别,实现方式不同]
3. window 是 BOM 对象，而非 js 对象；javacsript是通过访问BOM（Browser Object Model）对象来访问、控制、修改客户端(浏览器)

ECMAScript扩展知识：

① ECMAScript是一个标准，JS只是它的一个实现，其他实现包括ActionScript。

② “ECMAScript可以为不同种类的宿主环境提供核心的脚本编程能力……”，即ECMAScript不与具体的宿主环境相绑定，如JS的宿主环境是浏览器，AS的宿主环境是Flash。

###### ③ECMAScript描述了以下内容：语法、类型、语句、关键字、保留字、运算符、对象。
文档、网页、DOM、HTML之间近义词

https://blog.csdn.net/qq877507054/article/details/51395830

js即有函数，也有方法，方法是定义在对象里面的，js方法是包含函数定义的属性，方法是存储为对象属性的方法。

js 的 call 方法 ，函数.call（对象），这样相当于把这个函数变成这个对象的方法，搞清楚函数和方法的联系和区别

## ajax的5步：

**XMLHttpRequest**对象是ajax的基础

1.创建一个异步对象

 	var xmlhttp = new XMLHttpRequest();

2.设置请求方式和请求地址

​	xmlhttp.open(method,url,asysn);

​	xmlhttp.open("GET","请求地址egxxxx.php",true);

3.发送请求

​	get:		xmlhttp.send();

​	post:		xmlhttp.setRequestHeader("Content-type","application/x-www-form-urlencoded");

​				xmlhttp.send("id=111");

```

```

4.监听状态的变化，正常情况下，会被触发5次，01234

xmlhttp.onreadystatechange =  function(ev2){

​	//处理返回的结果，readyState是01234状态码

​	if(xmlhttp.readyState)

}

5处理返回的结果

来个例子：

function get(url,callback){

​	var oReq = new XMLHttpRequest()

​	oReq.onload = function(){  //用onload也行

​		callback(oReq.responseText)

​	}

​	oReq.open('get',url,true)

​	oReq.send()    //这个send函数放最后异步最好	

}

get('data.json',function(data){

​	.....

​	//对data的代码操作

})

responseText   获得字符串形式的数据（重点，多用于json）

responseXML   获得XML形式的响应数据。



后台向前端响应（发送json数据）

eg java语言





### 【】java没有函数，那叫方法，Java是面向对象的，要有面向对象的思维，

php分全局和局部变量，函数里面不能直接访问全局变量，要用global 关键字



可变函数类似回调函数，把函数当参数传递过去（不加括号）



### jquery的serialize() 方法通过序列化表单值，创建 URL 编码文本字符串。

一般直接把form表单序列化，会直接把name=value弄出来(光显示name=value)

您可以选择一个或多个表单元素（比如 input 及/或 文本框），或者 form 元素本身。

序列化的值可在生成 AJAX 请求时用于 URL 查询字符串中。

##### URL编码，URL编码遵循下列规则： 每对name/value由&；符分开；每对来自[表单](https://baike.baidu.com/item/%E8%A1%A8%E5%8D%95)的name/value由=符分开。如果用户没有输入值给这个name，那么这个name还是出现，只是无值。任何特殊的[字符](https://baike.baidu.com/item/%E5%AD%97%E7%AC%A6)（就是那些不是简单的七位ASCII，如汉字）将以百分符%用[十六进制编码](https://baike.baidu.com/item/%E5%8D%81%E5%85%AD%E8%BF%9B%E5%88%B6%E7%BC%96%E7%A0%81)，当然也包括象=,&；，和 % 这些特殊的字符。其实url编码就是一个字符ascii码的十六进制。不过稍微有些变动，需要在前面加上“%”。比如“\”，它的ascii码是92，92的十六进制是5c，所以“\”的url编码就是%5c。那么汉字的url编码呢？很简单，看例子：“胡”的ascii码是-17670，十六进制是BAFA，url编码是“%BA%FA”。

只会将”成功的控件“序列化为字符串。如果不使用按钮来提交表单，则不对提交按钮的值序列化。如果要表单元素的值包含到序列字符串中，元素必须使用 name 属性。