# php和AJAX

<?php

....

?>

变量用$

打印用 echo  或  print_r

键值对中间用  =>

上传文件必须设置 enctype="multpart/form-data"

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