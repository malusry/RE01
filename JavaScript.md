# 								JavaScript

## 2.快速入门

### 1.1引入		

1. 内部标签

   **注意不要使用自闭合标签**

```html
<script>
    //content......
</script>
```

2. 外部引入

   ```javascript
   //abc.js
   ```

   ```html
   <script src="abc.js"></script>
   ```

### 1.2  基本语法入门

<u>局部变量建议都使用 let 去定义</u>

```javascript
//严格检查模式,预防javascript的随意性导致产生的一些问题
//必须写在代码的第一行
'user strict';
//定义变量 变量类型 变量名 = 变量值
var score = 100;
let score = 100;
//console.log(score);打印变量,在浏览器的控制台打印变量
```

### 1.3数据类型

*数值,文本,图形,音频,视频......*

- number 

js不区分小数和整数

```javascript
123 	//整数
123.1	//浮点数
1.123e3	//科学计数法
-99		//负数
NaN		//not a number
Infinity//表示无限大
```

- 字符串

  "123" "abc"

- 布尔值

  true, 	false

- 运算逻辑

  &&	||	!

- 比较运算符

  ```
  =
  ==		等于(类型不一样,值一样,也会被判为true)
  ===		绝对等于(类型一样,值一样,结果为true)
  ```

  须知:

  - NaN===NaN,这个与所有的数值都不相等,包括自己
  - 只能通过isNaN来判断这个是否不是一个数

- null 和 undefined

  - null 空
  - undefined 未定义

- 数组

  java的数组必须是相同类型的对象,	js中不需要这样

  ```javascript
  //保证代码可读性,尽量使用	[]
  let arr = [1, 2, 3, 4, 5, 'helllo', null, true]
  
  ```

  取数组下标,如果越界了, 是

  对象

  对象时大括号, 数组是中括号

  > 每个属性之间使用逗号隔开,最后一个不需要添加

  ```javascript
  var Person = {
      name: "malus"
      age: 20
      tags: ['js', 'java', 'web']
  }
  ```

  

## 3.数据类型

### 3.1字符串

1. 

2. da

3. 多行字符串编写

   ```javascript
   var msg = `
   	hello
   	world
   	yeah~
   `
   ```

   

4. 模板字符串

   ```javascript
   let name = '';
   let age = 1;
   let msg = `hello ${name}`;
   ```

   

5. 字符串长度

   ```
   str.length
   ```

6. 字符串的可变性, 不可变

7. 大小写转换

   ```
   //注意这里是方法, 不是属性
   stu.toUpperCase();
   stu.toLowerCase();
   ```

8. stu.indexOf();

9. subString();      从给定的位置的字符串截取到最后一个字符串

### 3.2数组

Array可以包含任意的数据类型

1. 长度

   ```
   arr.length
   ```

   注意: 加入给arr.length赋值, 数组大小就会发生变化, 如果赋值过小,元素就会丢失

2. indexOf 通过元素获得下标索引

   ```
   arr.indexOf(1);
   ```

   字符串的 "1" 和 数字1 是不同的

3. slice()  截取Array的一部分,返回一个新数组, 类似于String中的 subString

4. push() 和 pop()

   ```
   push:	压入到尾部
   pop:	弹出尾部的一个元素
   ```

5. unshift(), shift() 头部

   ```
   unshift:	压入到头部
   shift:	弹出头部的一个元素
   ```

   

6. 排序 sort()

7. 元素反转revere()

8. concat()

   concat()并没有修改数组,只是返回一个新的数组

9. 连接符join

   打印拼接数组,使用特定的字符串连接

10. 多维数组

### 3.3对象

若干个键值对

```javascript
var 对象名 = {
    属性名: 属性值,
    属性名: 属性值,
    属性名: 属性值
}
//定义一个Person对象.有3个属性
var Person = {
    name: "malus"
    age: 20
    tags: ['js', 'java', 'web']
}
```

js中对象,{......}表示一个对象,键值对描述属性, 	多个属性用逗号隔开,最后一个属性不加逗号.

**javaScript中的所有键都是字符串, 值是任意对象!**

1. 对象赋值	Person.name = "NAME";

2. 使用一个不存在的对象属性, 不会报错!  undefined

3. 动态的删减属性, 通过delete删除对象的属性

   ```javascript
   delete person.name
   true
   ```

   

4. 动态的添加, 直接给新的属性添加值即可

   ```javascript
   person.aaa = "aaa";
   ```

   

5. 判断属性值是否在这个对象中!

6. 判断一个属性是否是这个对象自身拥有的hasOwnProperty()

   ```javascript
   person.hasOwnProperty('toString');
   false
   person.hasOwnProperty('age');
   true
   ```

### 3.4流程控制

1. if判断

2. while循环

3. for循环

   forEach 循环

   ```javascript
   var age = [];
   age.forEach(function (value) {
       console.log(value);
   });
   ```

### 3.5Map和Set

Map:

Set:

```javascript
set.add();//添加
set.delete();//删除
console.log(set.has(3));//是否包含某个元素
```

### 3.6	iterator

遍历数组

```javascript
//通过		for of 			/ 		for in 是下标
	for(var x of arr) {
		console.log(x);
}
```

遍历Map

```javascript
for(let x of map) {
		console.log(x);
}
```

遍历Set

```javascript
for(let x of set) {
		console.log(x);
}
```

## 4.函数

方法:	对象(属性, 方法)

函数:	调用

### 4.1定义函数

> 定义方式一

绝对值函数

```javascript
function abs(x) {
    return x;
}
```

一旦执行到return代表函数结束,返回结果.

如果没有执行return, 函数执行完也会返回结果, 结果就是undefined.

> 定义方式二

```javascript
var abs = function(x) {
    
}
```

> 调用函数

参数问题:javascript可以传任意个参数,也可以不传递参数

不存在参数时,手动抛出异常来判断

> argument
>
> 是js免费赠送的一个关键字

代表传递进来的所有参数,是一个数组

问题:	argument包含所有的参数, 有时候想使用多余的参数来进行附加操作.需要排除已有的参数.

> rest

```javascript
function method(a, b, ...rest) {
    console.log(rest);
    
}
```

rest参数只能写在最后,必须用 ... 标识

ES6引入的新特性, 获取除了已经定义的参数之外的所有参数...

### 4.2变量的作用域

在javascript中, var定义变量实际是有作用域的.

- 假设在函数体中声明,则在函数体外不可以使用 	(非想要实现的话,可以了解一下闭包)
- 如果两个函数使用了相同的变量名,只要在函数内部,就不冲突
- 内部函数可以访问外部函数的成员,反之则不行
- 假设在javascript中函数查找变量从自身函数开始, 由 内 向 外 查找.假设外部存在这个同名的函数变量,则内部函数会屏蔽外部函数的变量

> 提示变量的作用域

```javascript
function ex() {
    var x = 'x' + y;
    console.log(x);
    var y = 'y';
}
```

结果 : x undefined 说明js执行引擎,自动提示了y的声明, 但是不会提升变量y的赋值

```javascript
function ex() {
    var y;
    var x = 'x' + y;
    console.log(x);
    y = 'y';
}
```

这个在javascript建立之初就存在的特性. 所有的变量定义都放在函数的头部, 不要乱放,便于代码维护.

> 全局函数

全局变量window

默认所有的全局变量,都会自动绑定在 window 对象下.

alert()这个函数本身也是一个`window`变量;

javascript实际上只有一个全局作用域,任何变量(函数也可以视为变量),	假设没有在函数作用范围内找到, 就会向外查找, 如果在全局作用域都没有找到, 报错`referenceError`

> 规范

由于我们所有的全局变量都会绑定到我们的window上, 如果不同的js文件, 使用了相同的全局变量, 冲突->如何减少冲突

```javascript
//唯一全局变量
var useObj = {};

//定义全局变量
useObj.name = 'malus';
useObj.add = function (a, b) {
    return a + b;
}

```

把自己的代码全部放入自己定义的唯一空间名字中, 降低全局命名冲突的问题

Jquery 即 $

> 局部作用域	let

```javascript
function aaa() {
    for(let i = 0; i < 100; i++) {
        console.log(i);
    }
    console.log(i+1);//uncaught ReferenceError: i is not defined
}
```

建议都是使用let去定义局部作用域的变量;

> 常量 const

在ES6引入了常量关键字`const`

```javascript
const PI = '3.14';
console.log(PI);
```

### 4.3方法

```javascript

```

## 5.内部对象

> 标准对象 

```javascript
typeof 	123
"number"
typeof 	'123'
"string"
typeof 	true
"boolean"
typeof 	NaN
"number"
typeof	[]
"object"
typeof 	{}
"object"
typeof	Math.abs
"function"
typeof	undefined
"undefined"
```

### 5.1	Date

> 基本使用

```javascript
var now = new Date();
now.getFullYear();//年
now.getMonth();//月
now.getDate();//日
now.getDay();//星期几
now.getHours();//时
now.getMinutes();//分
now.getSeconds();//秒
now.getTime();//时间戳 全世界统一 当前时间距离1970.1.1 00::00:00 毫秒数
console.log(new Date(156879864356));//时间戳转为时间
```

转换

```javascript
var now = new Date(156879864356);
now.toLocaleString();
now.toGMTString();
```

### 5.2	JSON

- JSON: **J**ava**S**cript **O**bject **N**otation(JavaScript 对象表示法)
- JSON 是存储和交换文本信息的语法，类似 XML。
- JSON 比 XML 更小、更快，更易解析。
- JSON 易于人阅读和编写。
- C、Python、C++、Java、PHP、Go等编程语言都支持 JSON。

#### 什么是 JSON ？

- JSON 指的是 JavaScript 对象表示法（**J**ava**S**cript **O**bject **N**otation）
- JSON 是轻量级的文本数据交换格式
- JSON 独立于语言：JSON 使用 Javascript语法来描述数据对象，但是 JSON 仍然独立于语言和平台。JSON 解析器和 JSON 库支持许多不同的编程语言。 目前非常多的动态（PHP，JSP，.NET）编程语言都支持JSON。
- JSON 具有自我描述性，更易理解

在javascript一切皆为对象,任何js支持的类型都可以用JSON来表示;	number, string...

格式:

- ​	对象都用 	{}
- ​	数组都用     []
- ​     所有键值对都用 key:value

JSON字符串	和 	JS对象的转化

```javascript
var use = {
    a:"aaa",
    b:'bbb'
};
//对象转化为JSON字符串
var jsUser = JSON.stringify(user);
//JSON 字符串转化为对象 参数为JSON 字符串
var obj = JSON.parse('{"a":"aaa", "b":"bbb"}');
```

### 5.3 Ajax

- 原生的js写法 xhr异步请求
- jQuery封装好的 方法 $("#name").ajax("")
- axios 请求

## 6. 面向对象编程

> 原型对象

类:	模板

对象:	具体的实例

原型:	通过obj.\_\_proto\_\_  = protoObj	来实现

> class 和 类的继承

`class`关键字, 是在ES6引入的.

1. 定义一个类, 属性, 方法

```javascript
class Student {
    constructor(name) {
        this.name = name;
    }
}
```



2. 继承

```javascript
class College extends Student {
    constructor(name, grade) {
        super(name);
        this.grade = grade;
    }
}
```

本质: 还是原型对象

> 原型链

<img src="C:\Users\20102\AppData\Roaming\Typora\typora-user-images\image-20220722214000831.png" alt="image-20220722214000831" style="zoom:50%;" />

## 7.	操作BOM对象(重点)

> 浏览器介绍

JavaScript诞生就是为了能够让它在浏览器中运行!

BOM:	浏览器对象模型

浏览器内核:

- IE 6~11
- Chrome
- Safari
- FireFox

> window

window代表 浏览器窗口

> Navigator

Navigator, 封装浏览器的信息

大多数时候我们不会使用`navigator`对象,因为会被人为修改!

不建议使用这些属性来判断和编写代码

> screen

代表屏幕尺寸

> location   (重要)

location代表当前页面的URL信息

```javascript
host:""
href:""
protocol:"https:"
reload:f reload()	//刷新网页
//设置新的地址
location.assign('');
```

> document

document 代表当前页面, HTML	DOM文档树

获取具体的文档树节点

```javascript
var d1 = document.getElemById('app');
```

document可以直接获取cookie

```
document.cookie
```

劫持cookie原理:*加入获取cookie的js文件操作*

 服务器端可以设置cookie: httpOnly

> history

history 代表浏览器的历史记录

```
history.back();//后退
history.forward();//前进
```

## 8.操作DOM对象(重点)

> 核心

浏览器网页就是一个DOM树形结构

- 更新: 更新DOM节点
- 遍历DOM结点: 得到DOM节点
- 删除: 删除DOM节点
- 添加: 添加一个新的DOM节点

要操作一个DOM节点, 就首先要获得这个DOM节点.

```javascript
document.getElemById('id');
document.getElemByTagName('tag');
document.getElemByClassName('class');
```

> 更新节点

操作文本

- `id.innerText='123'`修改文本的值
- `id.innerHTML='<strong>123</strong>'可以解析HTML文本标签`

操作css

```javascript
id.style.color = 'red';//属性使用 字符串 包裹
id.style.fontSize = '20px';// 驼峰命名问题, 看提示
id.style.padding = '2em';
```

> 删除节点

删除节点的步骤:先获取父节点, 再通过父节点删除自己

```html
<script>
    var self = document.getElemById('p1');
	var father = p1.parentElement;
	father.removeChild(self);

	//删除是一个动态的过程
	father.removeChild(father.children[0]);
</script>

```

注意:删除多个节点的时候, children的 **大小** 和 **节点位置** 是时刻在变化的!

> 插入和创建节点

追加:

```html
<script>
	var js = document.getElemByID('js');
    var list = document.getElemByID('list');
    list.appendChild(js);// 追加到后面
</script>
```

> 创建一个新的标签, 实现插入

```html

```

## 9.操作表单(验证)

> 表单是 什么 form DOM 树

- 文本框    text
- 下拉框	<select>
- 单选框    radio
- 多选框    checkbox
- 隐藏域    hidden
- 密码框    password
- .......

表单的目的: 提交信息

> 获得要提交的信息