# php

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

​	xmlhttp.send();

4.监听状态的变化

xmlhttp.onreadystatechange =  function(ev2){

​	//处理返回的结果，readyState是01234状态码

​	if(xmlhttp.readyState)

}

5处理返回的结果





### 【】java没有函数，那叫方法，Java是面向对象的，要有面向对象的思维，

php分全局和局部变量，函数里面不能直接访问全局变量，要用global 关键字



可变函数类似回调函数，把函数当参数传递过去（不加括号）