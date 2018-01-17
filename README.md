# -写一些关于面试题目
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

### CSS
**CSS选择符有哪些？**
id（#mydiv） 类（.mydiv） 标签(div) 相邻(h1 + p) 子（ul>li）后代(ul li) 通配符（*) 属性（a[attr=""]） 伪类(a:hover)  </br>

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

### JS
**介绍JS的数据类型**</br>
基本类型：Undefined  Null Boolean String Number</br>
复杂：Object--细分为 Function Array</br>
null为对象，但是是空的，参与数值运算自动转为0</br>
undefined是window的一个特殊属性，未定义参与运算未NaN</br>
JS有两种数据类型：基本类型&引用类型(保存在内存中的对象)。

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




