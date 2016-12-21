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

