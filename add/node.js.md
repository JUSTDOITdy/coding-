# node.js

阮一峰和廖雪峰

https://nodejs.lipengzhou.com/01-web_concept.html

浏览器收到HTML响应内容后，就要开始从上到下依次解析，当在解析的过程中，发现：link script img iframe video audio 等等带有src 或者 href (link) 属性标签（具有外链的资源）的时候，浏览器会自动对这些资源发起新的请求，这就是一个网页会有这么多请求和响应的原因

form表单中需要提交的表单控件元素必须具有 name 属性

字符串中的转义要经常注意，路径中的\ 要写成 两个\

版本   x.x.x  , 第一个是大版本，改动较大，可能删除移除某些东西，第二个x只会增加某些东西，不会删，第三个x是修复某些bug的

art-template 模板引擎，后端的，搭配node.js的

php中无论是代码还是网页，都可以直接通过 web url路径来访问

node.js 由开发者处理 url 请求来允许你访问，给你返回

服务器重定向，301 永久重定向，会保存在本地   302 临时重定向

node的核心

- EcmaScript语言
- 核心模块
  + fs 文件操作的fs
  + http服务的http
  + url 
  + path
  + os 操作系统信息
- 第三方模块
  + art-template
- 自己写的代码和模块

require两次只会加载一次。不会重复加载。

node_modules一个项目只有一个，放在项目根目录，第三方模块查找机制先找node_modules/art-template/package.json，没有就找index.js,在没有往上找node_modules/xxx/package.json

每一个项目都要有一个package.json文件（包描述文件，就像产品说明书一样，就像java里面的pom.xml），可以通过npm init来用命令的方式生成package.json并创建一个项目，名字版本依赖入口（main）什么的 

npm命令行工具，有点像linux里面的软件包下载apt、rpm什么的，可以下载软件。 npm install 包名 --save

npm被墙问题，国内镜像http://npm.taobao.org/

先npm install  --global cnpm  下载国内的npm

然后cnpm install jquery

###### 热部署自动重启

npm install --global nodemon

nodemon xxx.js  //使用这个启动项目文件，项目文件只要修改并保存，就会自动重启

######  开放静态资源,url统一资源定位符，是某种映射关系

app.use('/a',express.static('../public/'))   //第一个/a是映射路径，相当于/public的别名

eg  127.0.0.1:4444/a/images.img   就是访问public文件夹里面的  images.img 

###### 返回页面,页面都放在view文件夹里，约定的，express默认去view里面找

res.render('xxx.html')   //render就是渲染的意思，返回字符串用send()

get和post，req.query可以获得get的?后面的参数，req.body用来获得post提交的数据，前提需要npm i -S body-parser插件

###### 现在大家都用koa2框架来开发node.js了

######  页面的样式可以去bootstrap官网上去找，复制源码修改一下即可

###### 凡是想要得到函数的异步操作结果的，必须通过回调函数来获取，函数也可以当成参数传到别的函数里，回调函数就是一个参数，将这个函数作为参数传到另一个函数里面，当那个函数执行完之后，再执行传进去的这个函数。这个过程就叫做回调。

