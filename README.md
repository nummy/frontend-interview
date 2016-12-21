## 前端面试题汇总

主要汇总自己在面试中遇到的问题和网络上收集到的问题。

### HTML/CSS部分

#### 1.什么是盒子模型？
在网页中，一个元素占有空间的大小由几个部分构成，其中包括元素的内容（content），元素的内边距（padding），元素的边框（border），元素的外边距（margin）四个部分。这四个部分占有的空间中，有的部分可以显示相应的内容，而有的部分只用来分隔相邻的区域或区域。4个部分一起构成了css中元素的盒模型。

#### 2.行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？
- 行内元素：a、b、span、img、input、strong、select、label、em、button、textarea
- 块级元素：div、ul、li、dl、dt、dd、p、h1-h6、blockquote
- 空元素：即系没有内容的HTML元素，例如：br、meta、hr、link、input、img

#### 3.CSS实现垂直水平居中
实现方法有很多种，以下是其中一种实现：

HTML结构：
```html
<div class="wrapper">
     <div class="content"></div>
</div>
```
CSS部分：
```css
.wrapper{position:relative;}
.content{
	background-color:#6699FF;
	width:200px;
	height:200px;
	position: absolute;        //父元素需要相对定位
	top: 50%;
	left: 50%;
	margin-top:-100px ;   //二分之一的height，width
	margin-left: -100px;
}
```
#### 4.简述一下src与href的区别
href 是指向网络资源所在位置，建立和当前元素（锚点）或当前文档（链接）之间的链接，用于超链接。

src是指向外部资源的位置，指向的内容将会嵌入到文档中当前标签所在位置；在请求src资源时会将其指向的资源下载并应用到文档内，例如js脚本，img图片和frame等元素。当浏览器解析到该元素时，会暂停其他资源的下载和处理，直到将该资源加载、编译、执行完毕，图片和框架等元素也如此，类似于将所指向资源嵌入当前标签内。这也是为什么将js脚本放在底部而不是头部。

#### 5.什么是CSS Hack?
一般来说是针对不同的浏览器写不同的CSS,就是 CSS Hack。

IE浏览器Hack一般又分为三种，条件Hack、属性级Hack、选择符Hack（详细参考CSS文档：css文档）。例如：
```
// 1、条件Hack
<!--[if IE]>
  <style>
		.test{color:red;}
  </style>
<![endif]-->
// 2、属性Hack
.test{
color:#090\9; /* For IE8+ */
*color:#f00;  /* For IE7 and earlier */
_color:#ff0;  /* For IE6 and earlier */
}
// 3、选择符Hack
* html .test{color:#090;}       /* For IE6 and earlier */
* + html .test{color:#ff0;}     /* For IE7 */
```

#### 6.简述同步和异步的区别
同步是阻塞模式，异步是非阻塞模式。

同步就是指一个进程在执行某个请求的时候，若该请求需要一段时间才能返回信息，那么这个进程将会一直等待下去，直到收到返回信息才继续执行下去；

异步是指进程不需要一直等下去，而是继续执行下面的操作，不管其他进程的状态。当有消息返回时系统会通知进程进行处理，这样可以提高执行的效率。

#### 7.px和em的区别

px和em都是长度单位，区别是，px的值是固定的，指定是多少就是多少，计算比较容易。em得值不是固定的，并且em会继承父级元素的字体大小。

浏览器的默认字体高都是16px。所以未经调整的浏览器都符合: 1em=16px。那么12px=0.75em, 10px=0.625em

#### 8.什么叫优雅降级和渐进增强？

渐进增强 progressive enhancement：
针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。

优雅降级 graceful degradation：
一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。

区别：
- 优雅降级是从复杂的现状开始，并试图减少用户体验的供给
- 渐进增强则是从一个非常基础的，能够起作用的版本开始，并不断扩充，以适应未来环境的需要
- 降级（功能衰减）意味着往回看；而渐进增强则意味着朝前看，同时保证其根基处于安全地带

#### 9.浏览器的内核分别是什么?
- IE: trident内核
- Firefox：gecko内核
- Safari：webkit内核
- Opera：以前是presto内核，Opera现已改用Google Chrome的Blink内核
- Chrome：Blink(基于webkit，Google与Opera Software共同开发)

### 编程题
1. 请使用2种以上的方法给array对象增加一个方法uniqO。用于把数组内容去重。[ =>解答](https://github.com/nummy/frontend-interview/blob/master/solutions/1.md)
2. 数组快速排序 [=>解答](https://github.com/nummy/frontend-interview/blob/master/solutions/2.md)
3. 请设计一个函数随机一注双色球号码，返回格式为字符串：”01，03，14，20，25，32｜09”。注：双色球分红球和蓝球，红球组成是从01-33、蓝球组成是01-16，一注可投注的号码为六个红球和一个蓝球组成，并且顺序从小到大排列。
4. 写一个对象深拷贝函数clone（对象可能是纯属数组或者各种类型的混合结构，可能层次很深），并将对象按照树形结构打印出来，注意缩进。
5. 请使用闭包的方式，写一段JS程序实现如下功能：函数每调用一次则该函数的返回值加1。 
6. 数组乱序

### 简答题
1. 在一次AJAX请求过程中，需要使用哪些对象创建的办法，还有AJAX请求过程中状态码的变化？AJAX和JSON、JSONP的实现原理，怎么解决AJAX的跨域问题？
2. cookie和session有什么区别？有没有什么关系？如果流星器禁用cookie的话，session还可以继续使用吗？
3. 谈谈网站web前端访问速度优化一些常用的方法和技巧。
4. web网站可能存在的安全隐患以及对应的解决办法
5. http常见状态码有哪些，分别代表什么含义？

