# -笔记
### HTML
**doctype的作用？**</br>
<!DOCTYPE>位于文档的第一行，告知浏览器的解析器是用什么标准解析这个文档。不存在或者错误的写，则以兼容模式呈现。</br>

**行内元素？块状元素？空(void)元素？**</br>
行内：img a span input select  </br>
块状：div ul ol h1~h6 p        </br>
空(没有闭合标签的)：  br hr img link input </br>

**页面样式导入使用link与@import的区别**</br>
页面被加载时，link会被同时加载。@import在页面被加载完再加载 </br>
link无兼容问题，@import>=IE5 </br>
@import会造成额外的请求</br>

**介绍一下浏览器内核的理解？**</br>
Trident:IE 360   Gecko:FF   Presto：Opera  Webkit：Safari，Chrome</br>
浏览器内核主要分为2部分：渲染引擎，JS引擎</br>
渲染引擎：取得页面的内容(html，xml等)</br>
JS引擎：解析和执行JS来实现页面的动态效果。</br>

**HTML5新增，移除了哪些元素？如何处理HTML5标签的兼容问题？如何区分HTML和HTML5**</br>
主要是关于图像，位置，存储，多任务等功能的增加。canvas video audio localStorage sessionStorage</br>
更好的语义化标签header nav footer aside section article</br>
表单控件calendar data time email</br>
新的技术webworker websocket Geolocation</br>

移除的元素：big font frame</br>

IE 6 7 8可以通过document.createElement方法产生标签，再添加默认样式</br>
还可以通过比较成熟的框架html5shim</br>

区分：DOCTYPE声明，新增的结构元素，功能元素</br>

**HTML语义化的理解**</br>
用正确的标签做正确的事情；让内容，结构更清晰，便于浏览器，搜索引擎解析。便于维护。</br>

**HTML5离线存储怎么使用？** </br>

**请描述cookies，localStorage，sessionStorage的区别？** </br>
cookies是为了标识用户身份而储存再客户端的数据(通常经过加密)，再浏览器与服务端传递。</br>
localStorage，sessionStorage仅仅存再本地。

存储大小：cookies <= 4K  localStorage，sessionStorage>5M</br>
有效时间：cookie在过期时间前一直有效  localStorage很久，除非主动删除 sessionStorage当前浏览器后自动删除</br>

**label的作用市什么？是怎么用的？**</br>
定义表单控件间的关系。</br>
label for="Name" Number: /label</br>
input type="text" name="Name"</br>
或者 label Date: input type="text" name="AAA" /label</br>

**如何实现多个标签页之间的通信？**</br>
webSocket ShareWorker;localStorage,sessionStorage</br>

**不使用border画出1px高的线，各浏览器各模式都能保持一致。**</br>
div{heighe:1px;background-color:red;overflow:hidden} //好像就IE5会出问题</br

**title与h1,b与strong,i与em的区别**</br>
title没有明确的意义，只是个标题。h1则表明层次的标题。</br>
同理b i都没有具体的语义化，知识改变样式。strong语气加强，em强调文本。</br>


### CSS
**CSS选择符有哪些？权重的定义？**
id（#mydiv） 类（.mydiv） 标签(div) 相邻(h1 + p) 子（ul>li）后代(ul li) 通配符（*) 属性（a[attr=""]） 伪类(a:hover)  </br>
id权重100    类权重10     标签权重1  eg .mydiv a{} 权重为10+1=11</br>

**哪些样式可以被继承？**</br>
可继承：font（一大家） text-indent text-align line-height  color 光标cursor</br>
不可继承：盒子模型属性(width height margin padding border) float position 

**CSS优先级算法如何计算？**</br>
越近越优先(内联>当前文件>外部文件)</br>
!import>id>class>tag</br>

**CSS3新增伪类有哪些？**</br>
p:first-of-type  p:only-of-type  :after :before :enable  :disable :checked</br>

**如何居中div**</br>
水平居中：</br>
1.margin:0 auto</br>
2.parent{position: relative;}  div{width: 300px;height: 300px; position: absolute; left: 50%;margin-left: -150px;}</br>
3.parent{display: flex;justify-content: center;} div{width: 300px;height: 300px;}</br>

水平垂直居中：</br>
1.div{width:300px;height:300px;position: absolute;top:50%;left:50%;margin-left:-150px;margin-top:-150px;}</br>
2.div{position: absolute;width: 300px;height: 300px;top:50%;left:50%;transform: translate(-50%, -50%);}</br>
3.parent{display: flex;align-items: center;justify-content: center;} div{width: 300px;height: 300px;}</br>

**position的值定位原点是？**</br>
relative:相对于其正常位置进行定位； absolute：相对于值不为static的第一个父元素进行定位；</br>
fixed：相对于浏览器窗口进行定位；</br> static：没有定位，正常流中； inherit：从父元素继承position属性；</br>

**CSS3有哪些新特性？**</br>
选择器： ：not(.inp) 所有class不为inp的节点</br>
圆角：border-radius   阴影box-shadow 文字特效 text-shadow 渐变gradient 动画transform animate</br>

**CSS3的Flexbox(弹性盒布局模型)，以及适用场景？**</br>
flexbox可以把列表放在同一个方向，上>下 左>右，并让别表能延伸到可占用的空间。复杂的布局可以嵌套flexContainer来实现。</br>
flex Container中的成员为flex item(项目)。</br>
常规布局是基于块和内联方向，而flex布局是基于flex-flow流的。</br>

**纯CSS制作一个三角形？**</br>
.demo{width:0;height:0;border-width:10px;border-style:solid;border-color:transparent transparent red transparent;}</br>

**满屏品字布局？**</br>
上面div100% 下面2个div50%浮动 不过IE7以下的滚动条会影响。overflow-y：hidden</br>

**常见的浏览器兼容问题有哪些？怎么解决的？常用的hack技巧？**</br>
1.浏览器默认的margin padding不同——————* margin：0；padding：0；</br>
2.chrome中文界面下会将小于12px的文字强制转换为12px------将文字包裹在span内设置为block块使用-webkit-transform：scale（）来缩小。</br>
3.几个img并排放，有些浏览器会有间距。-------使用float布局</br>
4.获取元素IE：document.idname或者document.getElementById('idName')其他浏览器也是后者。所以统一用后者。

**li与li之间的空白是什么原因引起的？怎么解决？**</br>
因为li换行后的空格产生了字符，变成一个空格。</br>
1：float；(不过焦点图不能设置浮动)2：所有li写在一行（代码不好看）;3:font-size:0(safari依然有)4:ul总letter-spacing=-8px;li中normal;</br>

**为什么要初始化CSS样式?**</br>
因为浏览器的兼容问题。如果不设置，往往会出现浏览器之间的页面显示差异。</br>
最好不要用* margin：0; padding:0;用到哪些，写哪些！</br>

**为什么要清除浮动？清除浮动的方式？**</br>
为了清除使用浮动元素产生的影响。浮动的元素，会使父元素高度塌陷，而高度的塌陷使我们页面后面的布局不能正常显示。</br>
1.给父元素加上height</br>
2.父元素也使用float</br>
3.使用伪类</br>
zoom是IE浏览器的专有属性，它可以设置或检索对象的缩放比例。解决IEixa比较奇葩的bug。</br>
外边距重叠，清除浮动，触发IE的haslayout

**对BFC(block formatting context)规范的理解？**</br>
(它是一个独立容器，决定了元素如何对其内容进行定位，以及与其他元素的关系和相互作用。)</br>
一个页面是由很多BOX组成的，元素的类型和display属性，决定了这个BOX的类型。</br>
不同类型的BOX，会参与不同的Formatting Context(决定如何渲染文档的容器)，因此Box内的元素会以不同的方式渲染，</br>
也就是说BFC内部的元素和外部的元素不会互相影响。</br>

**margin和padding分别适合什么场景使用？**</br>
margin是用来隔开元素的间距，padding是用来隔开元素与内容的间距。</br>
margin使元素之间互不干扰。padding使内容与包裹元素之间有间隔。</br>

**元素竖向的百分比是相对于容器的高度吗?**</br>
如margin-top margin-bottom padding-top padding-bottom是相对于父容器的高度。</br>

**什么是响应式设计？响应式基本原理是什么？如何兼容低版本的IE？**</br>
页面的设计和开发应当根据用户行为以及设备环境（系统平台，屏幕尺寸，屏幕定向等）进行相应的相应和调整。</br>
原理：通过媒体查询检测不同的设备屏幕尺寸做处理。</br>
meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no”</br>
兼容方案：。。。</br>




### JS
**介绍JS的数据类型**</br>
基本类型：Undefined  Null Boolean String Number</br>
复杂：Object--细分为 Function Array</br>
null为对象，但是是空的，参与数值运算自动转为0</br>
undefined是window的一个特殊属性，未定义参与运算未NaN</br>
==号无法区分null与undefin，===可以。</br>
JS有两种数据类型：基本类型&引用类型(保存在内存中的对象)。</br>

**JS原型，原型链有什么特点**</br>
每个对象都会在内部初始化一个属性---prototype(原型)</br>
访问某个属性，如果对象内部不存在--->去prototype查找--->prototype的prototype（Object内建对象）.这也就是原型链</br>
instance.constructor.prototype = instance._proto_

**JS如何实现继承？**</br>
1.构造继承 2.原型继承(prototype) 3.实例继承 4.拷贝继承(call,apply,bind)</br>
--见demo</br>

**JS创建对象的几种方式？**</br>
1.字面量方式：person:{sex:'max',age:18,name:'Jack'};</br>

2.用function来模拟无参的构造函数</br>
function Person(){};</br>
var peroson = new Person();</br>
person.name = 'Jack';</br>

3.this定义构造上下文</br>
function Person(name){</br>
  this.name = name;</br>
}</br>

4.prototype</br>

5.混合</br>
function Person(name){this.name = name;}</br>
Person.prototype.say = function(){alert("Name:"+this.name)}</br>
var peroson = new Person('AAA');</br>

**谈谈this对象？**</br>
1.总指向函数的直接调用者(非间接)；</br>
2.如有new关键字，this指向new出来的那个对象；</br>
3.在事件中，this指向触发这个事件的对象，特殊的是，IE中的attachEvent中的this总是指向全局对象window。</br>

**什么是window对象，什么是document对象？**</br>
window对象是指浏览器打开的窗口。</br>
document对象是 HTML文档对象的一个只读引用，window对象的一个属性。</br>

**什么是闭包？为什么要用它？**</br>
闭包是指有权访问另一个函数作用域中变量的函数，创建闭包的最常见的方式就是在一个函数内创建另一个函数，通过另一个函数访问这个函数的局部变量利用闭包可以突破作用域链域，将函数内部的变量与方法传递到外部。</br>
闭包的特性：</br>
1.函数内再嵌套函数</br>
2.内部函数可以引用外层参数和变量</br>
3.参数和变量不会被垃圾回收机制回收</br>

**JS中的use strict是什么意思？使用它区别是什么？**</br>
是ES5添加的(严格)运行模式，使得JS在更严格的条件下运行。</br>
使JS编码更加规范化，消除JS语法的一些不合理，不严谨之处，减少一些怪异行为。</br>
默认支持的糟糕特性都会被禁用，不能用with，不能在意外的情况下给全局变量赋值。</br>
提高编译器效率，增加运行速度。</br>

**new操作符具体干了什么？**</br>
1.创建一个空对象，并且this变量引用该对象，同时还继承了该函数的原型。</br>
2.属性和方法被加入到this引用的对象中。</br>
3.新创建的对象由this所引用，并且最后隐式的返回this。</br>
var obj = {}; obj._proto_ = Base.prototype; Base.call(obj);</br>

**JSON的了解？**</br>
JSON(JavaScript Object Notation)轻量级的数据交换格式。</br>
基于JS的一个子集。数据格式简单，易于读写，占用带宽小。</br>
{"age":"12","name":"Jack"}</br>

**DOM操作--添加，移除，移动，复制，创建和查找结点？**</br>
1.创建createElement() createTextNode()</br> 
2.添加append Child（）移除removeChild（）replaceChild() insertBefore()</br>
3.查找getElementsByTagName() getElementByName() getElementById()</br>


**Ajax是什么？如何创建一个Ajax？**</br>
异步(向服务器发送请求的时候不必等待，可以做其他事情。)传输+js+xml </br>
1.创建XMLHTTPRequest对象。</br>
2.创建一个新的HTTP请求，并指定HTTP请求的方法(send get)，URL及验证信息。</br>
3.设置相应HTTP请求状态变化的函数。</br>
4.发送HTTP请求。</br>
5.获取异步调用返回的数据。</br>
6.使用JS和DOM实现局部刷新。</br>

**如何解决跨域问题？**</br>

**模块化开发怎么做？**</br>
立即执行函数，不暴露私有成员。</br>
var module = （function(){ var m1 = function(){} var m2 = function(){} return m1:m1; m2:m2}）();





