# JQuery  是 JavaScript 的类库

放在<script></script> 标签里

jQuery是一个JavaScript函数库

基础语法： **$(selector).action()**   #id  .class

- 美元符号定义 jQuery
- 选择符（selector）"查询"和"查找" HTML 元素
- jQuery 的 action() 执行对元素的操作

实例:

- $(this).hide() - 隐藏当前元素
- $("p").hide() - 隐藏所有 <p> 元素
- $("p.test").hide() - 隐藏所有 class="test" 的 <p> 元素
- $("#test").hide() - 隐藏所有 id="test" 的元素



##### JavaScript有5种数据类型，**字符串值（string），数值（number），布尔值（boolean），数组，对象**(object)，数组即中括号【】**，对象即大括号{  }**，**里面是键值对，键即是属性**，键值即是属性值。

##### typeof 运算符对数组返回 "object"，因为在 JavaScript 中数组属于对象。函数是function



| $("*")                   | 选取所有元素                                            | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_all2) |
| ------------------------ | ------------------------------------------------------- | ------------------------------------------------------------ |
| $(this)                  | 选取当前 HTML 元素                                      | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_this) |
| $("p.intro")             | 选取 class 为 intro 的 <p> 元素                         | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_pclass) |
| $("p:first")             | 选取第一个 <p> 元素                                     | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_pfirst) |
| $("ul li:first")         | 选取第一个 <ul> 元素的第一个 <li> 元素                  | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_ullifirst) |
| $("ul li:first-child")   | 选取每个 <ul> 元素的第一个 <li> 元素                    | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_ullifirstchild) |
| $("[href]")              | 选取带有 href 属性的元素                                | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_hrefattr) |
| $("a[target='_blank']")  | 选取所有 target 属性值等于 "_blank" 的 <a> 元素         | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_hrefattrblank) |
| $("a[target!='_blank']") | 选取所有 target 属性值不等于 "_blank" 的 <a> 元素       | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_hrefattrnotblank) |
| $(":button")             | 选取所有 type="button" 的 <input> 元素 和 <button> 元素 | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_button2) |
| $("tr:even")             | 选取偶数位置的 <tr> 元素                                | [在线实例](https://www.runoob.com/try/try.php?filename=tryjquery_sel_even) |
| $("tr:odd")              | 选取奇数位置的 <tr> 元素                                |                                                              |

![1563506559109](C:\Users\howieDep\Desktop\picture\1563506559109.png)



# JQuery的扩展方法和插件编写

<https://www.cnblogs.com/MnCu8261/p/6039986.html>

https://www.cnblogs.com/gavin-num1/p/5655126.html

https://www.cnblogs.com/yuqingfamily/p/5775950.html

(function($){...})(jQuery)是什么意思
https://blog.csdn.net/rambo_china/article/details/7742321

![1563419701215](https://github.com/JUSTDOITdy/lantian/blob/master/image/1563419701215.png)

$.extend属于（类似于）静态类(对象)的静态方法，直接用 $.table.init(options);也只能用$.进行调用,类似工具类，可以添加静态对象和方法，$.对象.方法   或  $.方法

### JQuery.extend( ) 其实本身就是一个合并扩展JQuery类方法的方法（即给JQuery添加类（静态）方法），即是插件开发模式

1.1中讲的`$.extend()`的例子都是传了两个或两个以上的参数，但其实只有一个参数是必须的。若只传一个参数会怎样呢。

> 如果只有一个参数提供给`$.extend()`，这意味着目标参数被省略。在这种情况下，jQuery对象本身被默认为目标对象。这样，我们可以在jQuery的命名空间下添加新的功能。这对于插件开发者希望向 jQuery 中添加新函数时是很有用的。

$.fn.可以给$("#input1").调用方法

![1563421231431](https://github.com/JUSTDOITdy/lantian/blob/master/image/1563421231431.png)



# $.fn.extend 有两种写法

1.$.fn.extend({

​			ouput:function(args){

​				 

​			}

})

![1563421395040](https://github.com/JUSTDOITdy/lantian/blob/master/image/1563421395040.png)



通用js方法封装处理

{
(function ($) {

	$.extend({
		_tree: {},
		btTable: {},
		bttTable: {},
		// 表格封装处理
		table: {
			_option: {},
			// 初始化表格参数
			init: function(options) {
				    var defaults = {
	        			id: "bootstrap-table",
	        			type: 0, // 0 代表bootstrapTable 1代表bootstrapTreeTable
	    		  	  height: undefined,
	    		 	   sidePagination: "server",
	    		 	   ......
	    	        	    };
	      			  var options = $.extend(defaults, options);
	       			  $.table._option = options;
	        		  $.btTable = $('#' + options.id);
	          		  $.table.initEvent();
	         	      $('#' + options.id).bootstrapTable({
	             		   url: options.url,                                   // 请求后台的URL（*）
	              		   contentType: "application/x-www-form-urlencoded",   // 编码类型
	               		   method: 'post',                                     // 请求方式（*）
	                       cache: false,                                       // 是否使用缓存
	                       height: options.height,                             // 表格的高度
	                       striped: options.striped,                           // 是否显示行间隔色
	                       sortable: true,                                     // 是否启用排序
	                        ......
	                  });
	              } //init: function(options) {的}
			}//table的}   
		});//$.extend({后半部
})(jQuery);





# 事件  是html和Javascript本身就有，jquery也可以

事件通常与函数结合使用，函数不会在事件发生前被执行

# http://www.w3school.com.cn/tags/html_ref_eventattributes.asp>

## 1.html和Javascript 事件在标签里的一个属性，并且绑定一个方法。<button onclick="xxxx()">text<button>

![1563506559109](C:\Users\howieDep\Desktop\picture\onclick.png)

## 2.通过JQuery  $ 在【script】【/script】里面给标签增加事件和方法。

、![1563506559109](C:\Users\howieDep\Desktop\picture\jqueryonclick.png)

