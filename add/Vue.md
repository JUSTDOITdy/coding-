# Vue

{{xxx}},   原样输出data的字符串，里面也可以是个有返回值的方法{{add()}}

v-bind   属性绑定值  eg：<1a v-bind:href="xxx">随便<1/a>  //不用双大括号，用双引号

  				eg: <1input type="text"  v-bind:value="xxx">

v-html  将标签渲染成html ,eg    biaoqian:"<1a href='http://www.baidu.com'>随便<1/a>

​					<1p   v-html="biaoqian"><1/p>

v-on  (也可以用@)绑定事件





ref属性，和$refs，用来获取DOM的，就像id一样



js和jquery，React,等前端技术，面向对象的思想更多一些，DOM对象JQuery什么的，





npm是javascrpit的软件注册表，npm 为你和你的团队打开了连接整个 JavaScript 天才世界的一扇大门。它是世界上最大的软件注册表，每星期大约有 30 亿次的下载量，包含超过 600000 个 *包（package）* （即，代码模块）