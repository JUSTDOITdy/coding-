<https://blog.csdn.net/DayDayPlayPhone/article/details/51458619>

<http://blog.sina.com.cn/s/blog_73cf72f60102vj7s.html>

下载exe4j

用maven或export 产生出**jar包** ，找到需要的**jre**（可以在jdk里找，也可以用精简版jre）

打开exe4j，一步步执行，最关键的是JRE部分，把jre路径改成**./jre**，因为最后要把exe程序和jre文件夹放在同一个文件夹下，exe通过相对路径./jre找到jre（在无java环境的机子上），还有jdk1.8要用64位

最后产生exe和jre文件夹放在同一文件夹下，ok

