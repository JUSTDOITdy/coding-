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

