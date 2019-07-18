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

# JQuery的扩展方法和插件编写

https://www.cnblogs.com/gavin-num1/p/5655126.html

https://www.cnblogs.com/yuqingfamily/p/5775950.html

![1563419701215](https://github.com/JUSTDOITdy/lantian/blob/master/image/1563419701215.png)

$.extend属于（类似于）静态类(对象)的静态方法，直接用 $.table.init(options);也只能用$.进行调用,类似工具类，可以添加静态对象和方法，$.对象.方法   或  $.方法

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
