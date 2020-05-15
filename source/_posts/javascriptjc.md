---
title: 【二】JavaScript快速入门内容（简化路径）
date: 2020-05-15 15:54:05
tags:
  - JavaScript快速入门
  - 前端逻辑语言
categories:
  - JavaScript
description: JavaScript语法与事件
---

引用：https://www.runoob.com/js/js-tutorial.html

<!-- more -->

## 语法

> ### var，创建变量  

我们使用 var 关键词来声明变量：
```javascript
var carname;
```
变量声明之后，该变量是空的（它没有值）。
如需向变量赋值，请使用等号：
```javascript
carname="Volvo";
```
不过，您也可以在声明变量时对其赋值：
```javascript
var carname="Volvo";
```


> ### function，函数的基本使用  

##### 函数声明
在之前的教程中，你已经了解了函数声明的语法 :
```javascript
function functionName(chuangcan){
     执行的代码
}
```
函数声明后不会立即执行，会在我们需要的时候调用到。
实例:
```
<p id="demo"></p>
<script>
function fangfa(a,b){
      return a*b;
}
document.getElementById("demo").innerHTML=myFunction(4,3);
</script>
```

##### 函数表达式

JavaScript 函数可以通过一个表达式定义。
函数表达式可以存储在变量中：
```
<p>函数可以存储在变量中:</p>
<p id="demo"></p>
<script>
var x = function (a, b) {return a * b};
document.getElementById("demo").innerHTML = x(3,3);
</script>
```

在函数表达式存储在变量后，变量也可作为一个函数使用：
```
var x = function (a, b) {return a * b};
var z = x(4, 3);
```
以上函数实际上是一个 匿名函数 (函数没有名称)。
函数存储在变量中，不需要函数名称，通常通过变量名来调用。


##### Function() 构造函数
在以上实例中，我们了解到函数通过关键字 function 定义。
函数同样可以通过内置的 JavaScript 函数构造器（Function()）定义。
```
var myFunction = new Function("a","b","return a * b");
var x = myFunction(3,4);
```
实际上，你不必使用构造函数。上面实例可以写成：
```
var myFunction = function (a, b) {return a * b};
var x = myFunction(4, 3);
```


##### 函数提升（Hoisting）

提升（Hoisting）是 JavaScript 默认将当前作用域提升到前面去的的行为。
提升（Hoisting）应用在变量的声明与函数的声明。
因此，函数可以在声明之前调用：
```
myFunction(5);

function myFunction(y) {
    return y * y;
}
```


##### 自调用函数

函数表达式可以 "自调用"。
自调用表达式会自动调用。
如果表达式后面紧跟 () ，则会自动调用。
不能自调用声明的函数。
通过添加括号，来说明它是一个函数表达式：
```
<p>函数可以自动调用：</p>
<p id="demo"></p>
<script>
(function () {
    document.getElementById("demo").innerHTML = "Hello! 我是自己调用的";
})();
</script>
```


##### 函数可作为一个值使用

JavaScript 函数作为一个值使用：
```
<p>函数可作为一个值：</p>
<p>x = myFunction(4,3) 或 x = 12</p>
<p>两种情况下，x 的值都为 12。</p>
<p id="demo"></p>
<script>
function myFunction(a, b) {
    return a * b;
}
var x = myFunction(4, 3);
document.getElementById("demo").innerHTML = x;
</script>

```
JavaScript 函数可作为表达式使用：
```
<p>函数可作为一个表达式使用。</p>
<p id="demo"></p>
<script>
function myFunction(a, b) {
    return a * b;
}
var x = myFunction(4, 3) * 2;
document.getElementById("demo").innerHTML = x;
</script>

```
输出结果为24


##### 函数是对象

在 JavaScript 中使用 typeof 操作符判断函数类型将返回 "function" 。
但是JavaScript 函数描述为一个对象更加准确。
JavaScript 函数有 属性 和 方法。
arguments.length 属性返回函数调用过程接收到的参数个数：
```
<p> arguments.length 属性返回函数接收到参数的个数：</p>
<p id="demo"></p>
<script>
function myFunction(a, b) {
    return arguments.length;
}
document.getElementById("demo").innerHTML = myFunction(4, 3);
</script>
```
toString() 方法将函数作为一个字符串返回:
```
<p> toString() 将函数作为一个字符串返回：</p>
<p id="demo"></p>
<script>
function myFunction(a, b) {
    return a * b;
}
document.getElementById("demo").innerHTML = myFunction.toString();
</script>
```


##### 箭头函数

ES6 新增了箭头函数。
箭头函数表达式的语法比普通函数表达式更简洁。


(参数1, 参数2, …, 参数N) => { 函数声明 }
(参数1, 参数2, …, 参数N) => 表达式(单一)
// 相当于：(参数1, 参数2, …, 参数N) =>{ return 表达式; }


当只有一个参数时，圆括号是可选的：
(单一参数) => {函数声明}
单一参数 => {函数声明}


没有参数的函数应该写成一对圆括号:
() => {函数声明}


实例：
```
<p id="demo"></p>
​
<script>
const x = (x, y) => x * y;
document.getElementById("demo").innerHTML = x(5, 5);
</script>
```
输出25



> ### fn(xx)，函数传参  


##### 参数规则

- JavaScript 函数定义显式参数时没有指定数据类型。
- JavaScript 函数对隐式参数没有进行类型检测。
- JavaScript 函数对隐式参数的个数没有进行检测。

##### 默认参数

ES6 支持函数带有默认参数，就判断 undefined 和 || 的操作：
```
<p>设置参数的默认值。</p>
<p id="demo1"></p>
<p id="demo2"></p>
<script>
function myFunction(x, y = 10) {
    // 如果不传入参数 y ，则其默认值为 10
    return x + y;
}
// 输出 2
document.getElementById("demo1").innerHTML = myFunction(0, 2) ;
// 输出 15, y 参数的默认值
document.getElementById("demo2").innerHTML = myFunction(5);
</script>
```


##### 通过值传递参数

在函数中调用的参数是函数的隐式参数。
JavaScript 隐式参数通过值来传递：函数仅仅只是获取值。
如果函数修改参数的值，不会修改显式参数的初始值（在函数外定义）。
隐式参数的改变在函数外是不可见的。


##### 通过对象传递参数

在JavaScript中，可以引用对象的值。
因此我们在函数内部修改对象的属性就会修改其初始的值。
修改对象属性可作用于函数外部（全局变量）。
修改对象属性在函数外是可见的。



> ### 函数的调用  


##### 作为一个函数调用
```
function myFunction(a, b) {
    return a * b;
}
myFunction(10, 2);           // myFunction(10, 2) 返回 20

```
以上函数不属于任何对象。但是在 JavaScript 中它始终是默认的全局对象。
在 HTML 中默认的全局对象是 HTML 页面本身，所以函数是属于 HTML 页面。
在浏览器中的页面对象是浏览器窗口(window 对象)。以上函数会自动变为 window 对象的函数。
myFunction() 和 window.myFunction() 是一样的：
```
function myFunction(a, b) {
    return a * b;
}
window.myFunction(10, 2);    // window.myFunction(10, 2) 返回 20
```

##### 全局对象
当函数没有被自身的对象调用时 this 的值就会变成全局对象。
在 web 浏览器中全局对象是浏览器窗口（window 对象）。
该实例返回 this 的值是 window 对象:
```
function myFunction() {
    return this;
}
myFunction();                // 返回 window 对象
```

##### 函数作为方法调用
在 JavaScript 中你可以将函数定义为对象的方法。
以下实例创建了一个对象 (myObject), 对象有两个属性 (firstName 和 lastName), 及一个方法 (fullName):
```
var myObject = {
    firstName:"John",
    lastName: "Doe",
    fullName: function () {
        return this.firstName + " " + this.lastName;
    }
}
myObject.fullName();         // 返回 "John Doe"
```
fullName 方法是一个函数。函数属于对象。 myObject 是函数的所有者。
this对象，拥有 JavaScript 代码。实例中 this 的值为 myObject 对象。
测试以下！修改 fullName 方法并返回 this 值:
```
var myObject = {
    firstName:"John",
    lastName: "Doe",
    fullName: function () {
        return this;
    }
}
myObject.fullName();          // 返回 [object Object] (所有者对象)
```

##### 使用构造函数调用函数

如果函数调用前使用了 new 关键字, 则是调用了构造函数。
这看起来就像创建了新的函数，但实际上 JavaScript 函数是重新创建的对象：

```
// 构造函数:
function myFunction(arg1, arg2) {
    this.firstName = arg1;
    this.lastName  = arg2;
}
 
// This    creates a new object
var x = new myFunction("John","Doe");
x.firstName;                             // 返回 "John"
```
构造函数的调用会创建一个新的对象。新对象会继承构造函数的属性和方法。


##### 作为函数方法调用函数
在 JavaScript 中, 函数是对象。JavaScript 函数有它的属性和方法。
call() 和 apply() 是预定义的函数方法。 两个方法可用于调用函数，两个方法的第一个参数必须是对象本身。
```
function myFunction(a, b) {
    return a * b;
}
myObject = myFunction.call(myObject, 10, 2);     // 返回 20

```
```
function myFunction(a, b) {
    return a * b;
}
myArray = [10, 2];
myObject = myFunction.apply(myObject, myArray);  // 返回 20
```
两个方法都使用了对象本身作为第一个参数。 两者的区别在于第二个参数： apply传入的是一个参数数组，也就是将多个参数组合成为一个数组传入，而call则作为call的参数传入（从第二个参数开始）。
在 JavaScript 严格模式(strict mode)下, 在调用函数时第一个参数会成为 this 的值， 即使该参数不是一个对象。
在 JavaScript 非严格模式(non-strict mode)下, 如果第一个参数的值是 null 或 undefined, 它将使用全局对象替代。



> ### this，是个什么东西？  


面向对象语言中 this 表示当前对象的一个引用。
但在 JavaScript 中 this 不是固定不变的，它会随着执行环境的改变而改变。

- 在方法中，this 表示该方法所属的对象。
- 如果单独使用，this 表示全局对象。
- 在函数中，this 表示全局对象。
- 在函数中，在严格模式下，this 是未定义的(undefined)。
- 在事件中，this 表示接收事件的元素。
- 类似 call() 和 apply() 方法可以将 this 引用到任何对象。
```
<h2>JavaScript <b>this</b> 关键字</h2>
​
<p>实例中，<b>this</b> 指向了 <b>person</b> 对象。</p>
<p>因为 person 对象是 fullName 方法的所有者。</p>
​
<p id="demo"></p>
​
<script>
// 创建一个对象
var person = {
  firstName: "John",
  lastName : "Doe",
  id     : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
​
// 显示对象的数据
document.getElementById("demo").innerHTML = person.fullName();
</script>
```

##### 方法中的 this

在对象方法中， this 指向调用它所在方法的对象。
在上面一个实例中，this 表示 person 对象。
fullName 方法所属的对象就是 person。
```
fullName : function() {
  return this.firstName + " " + this.lastName;
}
```


##### 单独使用 this

单独使用 this，则它指向全局(Global)对象。
在浏览器中，window 就是该全局对象为 [object Window]:
```
<h2>JavaScript <b>this</b> 关键字</h2>

<p>实例中，<b>this</b> 指向了 window 对象:</p>

<p id="demo"></p>

<script>
var x = this;
document.getElementById("demo").innerHTML = x;
</script>
```
严格模式下，如果单独使用，this 也是指向全局(Global)对象。
```
<h2>JavaScript <b>this</b> 关键字</h2>

<p>实例中，<b>this</b> 指向了 window 对象:</p>

<p id="demo"></p>

<script>
"use strict";
var x = this;
document.getElementById("demo").innerHTML = x;
</script>

```


##### 函数中使用 this （默认）

在函数中，函数的所属者默认绑定到 this 上。
在浏览器中，window 就是该全局对象为 [object Window]:
```
<h2>JavaScript <b>this</b> 关键字</h2>
​
<p>实例中，<b>this</b> 表示 myFunction 函数的所有者：</p>
​
<p id="demo"></p>
​
<script>
document.getElementById("demo").innerHTML = myFunction();
function myFunction() {
  return this;
}
</script>
​
```


##### 函数中使用this（严格模式）
```
<h2>JavaScript <b>this</b> 关键字</h2>

<p>函数中，默认情况下，<b>this</b> 指向全局对象。</p>
<p>严格模式下，<b>this</b> 为 <b>undefined</b>，因为严格模式下不允许默认绑定:</p>

<p id="demo"></p>

<script>
"use strict";
document.getElementById("demo").innerHTML = myFunction();
function myFunction() {
  return this;
}
</script>
```


##### 事件中的 this
在 HTML 事件句柄中，this 指向了接收事件的 HTML 元素：
```
<button onclick="this.style.display='none'">
点我后我就消失了
</button>
```


##### 对象方法中的绑定
下面实例中，this 是 person 对象，person 对象是函数的所有者：
```
var person = {
  firstName  : "John",
  lastName   : "Doe",
  id         : 5566,
  myFunction : function() {
    return this;
  }
};

```

```
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```
说明: this.firstName 表示 this (person) 对象的 firstName 属性。


##### 显式函数绑定

在 JavaScript 中函数也是对象，对象则有方法，apply 和 call 就是函数对象的方法。这两个方法异常强大，他们允许切换函数执行的上下文环境（context），即 this 绑定的对象。
在下面实例中，当我们使用 person2 作为参数来调用 person1.fullName 方法时, this 将指向 person2, 即便它是 person1 的方法：

```
var person1 = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
var person2 = {
  firstName:"John",
  lastName: "Doe",
}
person1.fullName.call(person2);  // 返回 "John Doe"
```
结语-
this 的多种指向:
 - 1、在对象方法中， this 指向调用它所在方法的对象。
 - 2、单独使用 this，它指向全局(Global)对象。
 - 3、函数使用中，this 指向函数的所属者。
 - 4、严格模式下函数是没有绑定到 this 上，这时候 this 是 undefined。
 - 5、在 HTML 事件句柄中，this 指向了接收事件的 HTML 元素。
 - 6、apply 和 call 允许切换函数执行的上下文环境（context），即 this 绑定的对象，可以将 this 引用到任何对象。




> ### for循环

如果您希望一遍又一遍地运行相同的代码，并且每次的值都不同，那么使用循环是很方便的。
我们可以这样输出数组的值：
```
for (var i=0;i<cars.length;i++)
{ 
    document.write(cars[i] + "<br>");
}
```

##### 不同类型的循环
JavaScript 支持不同类型的循环：
- for - 循环代码块一定的次数
- for/in - 循环遍历对象的属性
- while - 当指定的条件为 true 时循环指定的代码块
- do/while - 同样当指定的条件为 true 时循环指定的代码块


##### For循环
for 循环是您在希望创建循环时常会用到的工具。

下面是 for 循环的语法：
for (语句 1; 语句 2; 语句 3)
{
    被执行的代码块
}
- 语句 1 （代码块）开始前执行
- 语句 2 定义运行循环（代码块）的条件
- 语句 3 在循环（代码块）已被执行之后执行

```
<p id="demo"></p>
<script>
function myFunction(){
	var x="";
	for (var i=0;i<5;i++){
		x=x + "该数字为 " + i + "<br>";
	}
	document.getElementById("demo").innerHTML=x;
}
</script>
```
从上面的例子中，您可以看到：
Statement 1 在循环开始之前设置变量 (var i=0)。
Statement 2 定义循环运行的条件（i 必须小于 5）。
Statement 3 在每次代码块已被执行后增加一个值 (i++)。


语句 1
通常我们会使用语句 1 初始化循环中所用的变量 (var i=0)。
语句 1 是可选的，也就是说不使用语句 1 也可以。
您可以在语句 1 中初始化任意（或者多个）值：
```
<script>
cars=["BMW","Volvo","Saab","Ford"];
for (var i=0,l=cars.length; i<l; i++){
	document.write(cars[i] + "<br>");
}
</script>
```


语句 2
通常语句 2 用于评估初始变量的条件。
语句 2 同样是可选的。
如果语句 2 返回 true，则循环再次开始，如果返回 false，则循环将结束。


语句 3
通常语句 3 会增加初始变量的值。
语句 3 也是可选的。
语句 3 有多种用法。增量可以是负数 (i--)，或者更大 (i=i+15)。
语句 3 也可以省略（比如当循环内部有相应的代码时）：
```
<script>
cars=["BMW","Volvo","Saab","Ford"];
var i=0,len=cars.length;
for (; i<len; ){
    document.write(cars[i] + "<br>");
    i++;
}
</script>
```


##### For/In 循环
JavaScript for/in 语句循环遍历对象的属性：
```
<p>点击下面的按钮，循环遍历对象 "person" 的属性。</p>
<button onclick="myFunction()">点击这里</button>
<p id="demo"></p>
<script>
function myFunction(){
	var x;
	var txt="";
	var person={fname:"Bill",lname:"Gates",age:56}; 
	for (x in person){
		txt=txt + person[x];
	}
	document.getElementById("demo").innerHTML=txt;
}
</script>
```
您将在有关 JavaScript 对象的章节学到更多有关 for / in 循环的知识。



> ### []、{}，数组对象


##### JavaScript 数组

下面的代码创建名为 cars 的数组：
```
var cars=new Array();
cars[0]="Saab";
cars[1]="Volvo";
cars[2]="BMW";
```
或者 (condensed array):
```
var cars =new Array("Saab","Volvo","BMW");
```
或者 (literal array):
```
<script>
var i;
var cars = new Array();
cars[0] = "Saab";
cars[1] = "Volvo";
cars[2] = "BMW";

for (i=0;i<cars.length;i++)
{
document.write(cars[i] + "<br>");
}
</script>
```

注：数组下标是基于0的，所以第一个项目是 [0]，第二个是 [1]，以此类推。



> ### JavaScript 对象

对象由花括号分隔。在括号内部，对象的属性以名称和值对的形式 (name : value) 来定义。属性由逗号分隔：
```
var person={firstname:"John", lastname:"Doe", id:5566};
```
上面例子中的对象 (person) 有三个属性：firstname、lastname 以及 id。
空格和折行无关紧要。声明可横跨多行：
```
var person={
firstname : "John",
lastname  : "Doe",
id        :  5566
};
```
对象属性有两种寻址方式：
```
<script>
var person=
{
	firstname : "John",
	lastname  : "Doe",
	id        :  5566
};
document.write(person.lastname + "<br>");
document.write(person["firstname"] + "<br>");
</script>
```



> ### for in 循环，操作键值对


##### for in 循环
for...in 语句用于遍历数组或者对象的属性（对数组或者对象的属性进行循环操作）。
for ... in 循环中的代码每执行一次，就会对数组的元素或者对象的属性进行一次操作。

语法：
```
for (变量 in 对象)
{
    在此执行代码
}

```

“变量”用来指定变量，指定的变量可以是数组元素，也可以是对象的属性。(也就是说变量是用来循环数组或对象的)

实例（使用 for ... in 循环遍历数组。）：
```
<html>
<body>

<script type="text/javascript">
var x
var mycars = new Array()
mycars[0] = "Saab"
mycars[1] = "Volvo"
mycars[2] = "BMW"

for (x in mycars)
{
document.write(mycars[x] + "<br />")
}
</script>

</body>
</html>
```


##### 操作键值对

字典 是一种以键-值对形式存储数据的数据结构，比如：名字-电话号码，通过名字就能找到对应的电话号码，名字就是键(key),电话号就是值(value)。
字典中的键，是值在字典中的索引。
对于javascript来说，字典类(Dictionary)的基础是Array类，js中的Array既是一个数组，同时也是一个字典。
```
var dic = {c:4, a:2, d:3, b:1}; // 定义一个字典

    console.log("输出最初的字典元素: "); 
    for(var key in dic){
        console.log("key: " + key + " ,value: " + dic[key]);
    }

    console.log("字典元素按key值排序: ");
    var res = Object.keys(dic).sort(); 
    for(var key in res){
        console.log("key: " + res[key] + " ,value: " + dic[res[key]]);
    }

    console.log("字典元素按value值排序: ");
    var res2 = Object.keys(dic).sort(function(a,b){ return dic[a]-dic[b]; });
    for(var key in res2){
        console.log("key: " + res2[key] + " ,value: " + dic[res2[key]]);
    }
```

简单的字典操作：
```
 var dic = new Array(); //定义一个字典
 dic['one'] = '1';      // 添加字典的元素( key:value)
```



> ### document 是什么？

##### Window 对象

Window 对象表示浏览器中打开的窗口。
如果文档包含框架（frame 或 iframe 标签），浏览器会为 HTML 文档创建一个 window 对象，并为每个框架创建一个额外的 window 对象。
注释：没有应用于 window 对象的公开标准，不过所有浏览器都支持该对象。


##### Window 对象描述
Window 对象表示一个浏览器窗口或一个框架。在客户端 JavaScript 中，Window 对象是全局对象，所有的表达式都在当前的环境中计算。也就是说，要引用当前窗口根本不需要特殊的语法，可以把那个窗口的属性作为全局变量来使用。例如，可以只写 document，而不必写 window.document。
同样，可以把当前窗口对象的方法当作函数来使用，如只写 alert()，而不必写 Window.alert()。
除了上面列出的属性和方法，Window 对象还实现了核心 JavaScript 所定义的所有全局属性和方法。
Window 对象的 window 属性和 self 属性引用的都是它自己。当你想明确地引用当前窗口，而不仅仅是隐式地引用它时，可以使用这两个属性。除了这两个属性之外，parent 属性、top 属性以及 frame[] 数组都引用了与当前 Window 对象相关的其他 Window 对象。


##### Document 对象
每个载入浏览器的 HTML 文档都会成为 Document 对象。
Document 对象使我们可以从脚本中对 HTML 页面中的所有元素进行访问。
提示：Document 对象是 Window 对象的一部分，可通过 window.document 属性对其进行访问。


##### Document 对象描述
HTMLDocument 接口对 DOM Document 接口进行了扩展，定义 HTML 专用的属性和方法。
很多属性和方法都是 HTMLCollection 对象（实际上是可以用数组或名称索引的只读数组），其中保存了对锚、表单、链接以及其他可脚本元素的引用。
这些集合属性都源自于 0 级 DOM。它们已经被 Document.getElementsByTagName() 所取代，但是仍然常常使用，因为他们很方便。
write() 方法值得注意，在文档载入和解析的时候，它允许一个脚本向文档中插入动态生成的内容。
注意，在 1 级 DOM 中，HTMLDocument 定义了一个名为 getElementById() 的非常有用的方法。在 2 级 DOM 中，该方法已经被转移到了 Document 接口，它现在由 HTMLDocument 继承而不是由它定义了。




> ###  操作dom

##### createElement() 方法

创建一个按钮:
```
var btn=document.creaElement("button");
```


HTML元素经常包含文本。创建指定文本的按钮你需要在按钮元素后添加文本节点:
创建指定文本的按钮：
```
<p id="demo">单击按钮创建有文本的按钮</p>
<button onclick="myFunction()">点我</button>
<script>
function myFunction(){
	var btn=document.createElement("BUTTON");
	var t=document.createTextNode("CLICK ME");
	btn.appendChild(t);
	document.body.appendChild(btn);
};

</script>
```


##### appendChild() 方法

添加列表项：
```
document.getElementById("myList").appendChild(newlist)
```

完整代码：
```
<ul id="myList"><li>Coffee</li><li>Tea</li></ul>
<p id="demo">单击按钮将项目添加到列表中</p>
<button onclick="myFunction()">点我</button>
<script>
function myFunction(){
    var node=document.createElement("LI");
    var textnode=document.createTextNode("Water");
    node.appendChild(textnode);
    document.getElementById("myList").appendChild(node);
}
</script>
<p><strong>注意:</strong><br>首先创建一个节点，<br> 然后创建一个文本节点，<br>然后将文本节点添加到LI节点上。<br>最后将节点添加到列表中。</p>
​
```

定义和用法--转移某个列表项到另外一个列表项：
```
<ul id="myList1"><li>Coffee</li><li>Tea</li></ul>
<ul id="myList2"><li>Water</li><li>Milk</li></ul>
<p id="demo">单击按钮将项目从一个列表移动到另一个列表中</p>
<button onclick="myFunction()">点我</button>
<script>
function myFunction(){
	var node=document.getElementById("myList2").lastChild;
	document.getElementById("myList1").appendChild(node);
}
</script>

```


##### innerHTML 属性

定义和用法
innerHTML 属性设置或返回表格行的开始和结束标签之间的 HTML。

语法:
```
HTMLElementObject.innerHTML=text
```

实例(改变文本，URL，及链接目标)：
```<script>
function changeLink(){
	document.getElementById('myAnchor').innerHTML="RUNOOB";
	document.getElementById('myAnchor').href="//www.runoob.com";
	document.getElementById('myAnchor').target="_blank";
}
</script>
</head>
<body>
 
<a id="myAnchor" href="//www.microsoft.com">Microsoft</a>
<input type="button" onclick="changeLink()" value="修改链接">
```


##### setAttribute(n,m)

作用：用来添加标签的类型属性


定义和用法：
setAttribute() 方法创建或改变某个新属性。
如果指定属性已经存在,则只设置该值。


语法
```
Element.setAttribute(type,button)
```

实例：
```
​
<input value="">
​
<p id="demo">点击下面的按钮来设置按钮的类型属性。</p>
<button onclick="myFunction()">点我</button>
<script>
function myFunction(){
    document.getElementsByTagName("INPUT")[0].setAttribute("type","button"); 
};
</script>
<p>Internet Explorer 8 及更早的版本不支持 setAttribute 方法。</p>
​
```




## 事件

##### onclick

当按钮被点击时执行Javascript代码：:
```
<script>
function myFunction(){
	document.getElementById("demo").innerHTML="Hello World";
}
</script>
</head>
<body>

<p>单击按钮触发函数。</p>
<button onclick="myFunction()">点我</button>
<p id="demo"></p>
```


定义和用法
onclick 时间会在元素被点击时发生。


语法
HTML中：
```
<element onclick="SomeJavaScriptCode">
```
JavaScript 中：
```
object.onclick=function(){SomeJavaScriptCode};
```