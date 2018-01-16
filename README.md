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


### CSS
**CSS选择符有哪些？**
id（#mydiv） 类（.mydiv） 标签(div) 相邻(h1 + p) 子（ul>li）后代(ul li) 通配符（*) 属性（a[attr=""]） 伪类(a:hover)  </br>

**哪些样式可以被继承？**</br>
可继承：font（一大家） text-indent text-align line-height  color 光标cursor</br>
不可继承：盒子模型属性(width height margin padding border) float position 

**CSS优先级算法如何计算？**</br>
越近越优先(内联>当前文件>外部文件)</br>
!import>id>class>tag</br>

###JS
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
1.构造继承 2.原型继承 3.实例继承 4.拷贝继承



