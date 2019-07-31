# Vue

{{xxx}},   原样输出data的字符串，里面也可以是个有返回值的方法{{add()}}

v-bind   属性绑定值  eg：<1a v-bind:href="xxx">随便<1/a>  //不用双大括号，用双引号

  				eg: <1input type="text"  v-bind:value="xxx">

v-html  将标签渲染成html ,eg    biaoqian:"<1a href='http://www.baidu.com'>随便<1/a>

​					<1p   v-html="biaoqian"><1/p>

v-on  (也可以用@)绑定事件





ref属性，和$refs，用来获取DOM的，就像id一样