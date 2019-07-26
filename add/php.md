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