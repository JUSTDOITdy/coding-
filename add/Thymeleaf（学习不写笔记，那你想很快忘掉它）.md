## Thymeleaf（学习不写笔记，那你想很快忘掉它）

### href=,  

### 不要直接跳静态的src/main/resources/templates里面的.html页面，要走Controller层，经过Controller的解析返回.html的页面

1.导入命名空间，可以有语法提示 <html lang="en" xmlns:th="http://www.thymeleaf.org">

2.th:text   文本内容        th的任意属性都可以替换原生属性的词，

eg:   th:id="${...}"   th:class="${...}"  这些前端的标签属性都可以替换

如果是需要字符串与model中的值进行拼接的话，写法为th:text="'字符串'+${model的name}"

```javascript
th:text="'姓名：'+${childD.name}"
```

3.th:text 和 th:utext ，后者会渲染html，前者原样输出

4.行内（内联）写法，双中括号[[...]]就是th:text  ，中括号小括号[(...)]就是th:utext

可以在Javascript<script th:inline="javascript"></script>里面使用 [[${...}]  或  [(${...})]

·<p th:text="'hello,'+${session.user.name}">xxxx</p>

等于

·<p>hello,[[${session.user.name}]]</p>

（必须前面加点东西才不会被渲染成html，a）

5.th:each=${...} 写在那个标签，就会重复生成哪个标签

6.![1563330604455](https://github.com/JUSTDOITdy/codingNote/blob/master/image/1563330604455.png)

7.thymeleaf有一些工具类（对象），数字的(Numbers)、字符串的、日期的（dates）、数组和集合的

8.![1563334693965](https://github.com/JUSTDOITdy/codingNote/blob/master/image/1563334693965.png)

th:if=“...”   进行判断，如果里面是0、false、off、no否定意思的东西，就不显示

th:with  是原来给某变量赋值的

9.![1563335030687](https://github.com/JUSTDOITdy/codingNote/blob/master/image/1563335030687.png)

![1563335385772](https://github.com/JUSTDOITdy/codingNote/blob/master/image/1563335385772.png)

观察设置Map变量的方式，很多地方需要用Map，键值对，前端需要用键“userMap”来取值

![1563355154848](https://github.com/JUSTDOITdy/codingNote/blob/master/image/1563355154848.png)
