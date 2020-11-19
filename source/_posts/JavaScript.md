---
title: JavaScript
toc: true
mathjax: true
categories:
  - JavaScript
tags:
  - js
date: 2020-11-11 21:10:21
summary:
cover:
coverImg:
top:
img:
---

# JavaScript

## 变量 let

```js
/*
let没有变量提升 
一般用于块级作用域

*/
```

常量 const

```js
/*
常量名一般都是大写 
定义常量时直接给常量初始化

*/
eg:
const PI = 3.14;
```

## 删除数组元素

```js
/*
delete arr[1];
注意:删除数组元素后,位置保留,当前数组元素的值为undefined

*/
```

## 数组的遍历

```js
/*
for of循环:
for(var ele of arr){
	console.log(ele);
}
注意:ele是数组的元素,不是下标

forEach循环:
arr.forEach(function(ele, index){
	console.log(ele + '===' + index);
});
注意:形参ele为数组元素,index为数组下标

*/
```

## 数组对象的方法

```js
/*
1. find方法
1) 作用: find()方法返回通过测试(函数内判断)的数组的第一个元素的值
2) 格式: arr.find(function(val, index, arr){return val > 50})

2. findIndex方法
1) 作用: findIndex()方法返回通过测试(函数内判断)的数组的第一个元素的下标
2) 格式: arr.findIndex(function(val, index, arr){return val > 50})

3. map方法
1) 作用: map()方法返回一个新数组,数组中的元素为原始数组元素调用函数处理后的值,不会对空数组进行检测
2) 格式: arr.map(function(val, index, arr){})

4. some方法
1) 作用: some()方法用于检测数组中的元素是否满足指定条件(函数提供).有满足条件的返回true,否则返回false
2) 格式: arr.some(function(val, index, arr){return val > 3})

5. every方法
1) 作用: every()方法用于检测数组中所有元素是否都符合指定条件
2) 格式: arr.every(function(val, index, arr){return val > 3})

6. includes方法
1) 作用: includes()方法用来判断一个数组是否包含一个指定的值,如果是返回true,否则返回false
2) 格式: arr.includes(seachElement, fromIndex)

7. filter方法
1) 作用: 从数组中过滤出符合条件的数组元素,返回值为由这些元素形成的新的数组
2) 格式: arr.filter(function(val, index, arr){return 条件})

*/
```

## 对象的方法

```js
/*
1. 利用Object.keys方法获取对象的所有属性
格式: Object.keys(obj) 
返回一个数组

2. 利用Object.values方法获取对象的所有属性值
格式: Object.values(obj)
返回一个数组

3. 利用Object.entries方法获取对象中所有的属性名和属性值
格式: Object.entries(obj)
返回一个二维数组

*/
```

## Math对象的属性和方法

```js
/*
1. PI属性
作用: 获取圆周率
格式: Math.PI

2. ceil方法
作用: 对数据进行向上取整,取最小整数
格式: Math.ceil(num)

3. floor方法
作用: 对数据进行向下取整,取最大整数
格式: Math.floor(num)

4. round方法
作用: 对数据进行四舍五入,取整数,对小数点后一位做四舍五入
格式: Math.round(num)

5. pow方法
格式: Math.pow(x,y)
作用: 求x的y次方

6. max方法
作用: 求数据的最大值
格式: Math.max(num1, num2, num3, ...)
不可以直接传数组 可以通过...arr方法传参

7. min方法
作用: 求数据的最小值
格式: Math.min(num1, num2, num3, ...)
不可以直接传数组 可以通过...arr方法传参

8. abs方法
作用: 求数据的绝对值
格式: Math.abs(num)

9. sqrt方法
作用: 求数据的算数平方根
格式: Math.sqrt(num)

10. random方法
作用: 返回0-1的随机小数,包含0,但是不包含1
格式: Math.random()
利用random方法生成n-m的随机整数,包含n和m
公式: parseInt(Math.random() * (最大值 - 最小值 + 1) + 最小值)

*/
```

## 日期和时间对象

```js
/*
1. 创建日期和时间对象
1) var date1 = new Date();//表示创建系统当前的日期时间对象
2) var date2 = new Date('2020-1-1 12:30:33');//将指定的日期时间字符串转换为日期
3) var date3 = new Date(1000);//返回的是距离1970年1月1日0时0分0秒的时间点 (注意: 北京位于东八区 比标准时间多8小时)

2. 日期时间对象的方法
1) date.getFullYear() //获取年份返回的是number类型
2) date.getYear() //返回距离1900年的年份
3) date.getMonth() //返回月份 注意: 返回值为0-11 0表示1月 11表示12月
4) date.getDate() //返回天
5) date.getDay() //返回星期 注意: 返回值为0-6 0表示星期日 1表示星期1
6) date.getHours() //返回小时
7) date.getMinutes() //返回分钟
8) date.getSeconds() //返回秒
9) date.getTime() //距离1970年1月1日0时0分0秒的毫秒值
10) date.toLocalString() //包含时间和日期
11) date.toLocalDateString() //只包含日期
12) date.toLocalTimeString() //只包含时间

*/
```

## 字符串

```js
/*
1. 创建字符串对象
1) 方式一: 利用构造方法String
var str = new String('hello');

2) 方式二: 利用字面量形式
var str = 'hello';

// 基本数据类型的字符串之所以能调用字符串对象的属性和方法,是因为在调用这些属性和方法的那一刻,后台会自动将基本类型的字符串包装成字符串对象,然后调用字符串的属性和方法,在调用完毕后,又将这个字符串对象转换为基本的数据类型.

2. 字符串对象的方法
1) startsWith方法
作用: 判断字符串是否以某个字符开头.如果是则返回true 否则返回false
格式: str.startsWith('字符')

2) endsWith方法
作用: 判断字符串是否以某个字符结尾.如果是则返回true 否则返回false
格式: str.endsWith('字符')

3) repeat方法
作用: 返回一个新字符串,表示将原字符串重复n次
格式: str.repeat(3)

4) padStart方法
作用: 将字符串扩展到指定的长度,如果长度不够,那么在字符串的开头以指定字符补位
格式: str.padStart(长度, '指定字符')
注意: 如果指定的长度小于字符串现有的长度,那么不需要补位,直接返回字符串本身

5) padEnd方法
作用: 将字符串扩展到指定的长度,如果长度不够,那么在字符串的末尾以指定字符补位
格式: str.padEnd(长度, '指定字符')
注意: 如果指定的长度小于字符串现有的长度,那么不需要补位,直接返回字符串本身

3. 字符串的编码方法
1) btoa方法 编码
作用: 按照Base64的编码方式,对字符串进行编码
格式: btoa(str)

atob方法 解码
作用: 按照Base64编码方式得到的字符串解码回原有的字符串
格式: atob(str)

2) encodeURIComponent方法 编码
作用: 将非ASCII码转换为Base64编码
格式: encodeURIComponent(str)

decodeURIComponent方法 解码
作用: 将转码后的内容转为非ASCII码内容
格式: decodeURIComponent(str)

*/

eg: 字符串解析 将不能直接被使用的数据通过解析变成可以被直接使用的数据 
var data = '?age=10&score=90&height=175';//window.location.search获取的字符串的格式
var infoArr = window.location.search.slice(1).split('&');
var obj = {};//用来存储参数
for(var i=0; i<infoArr.length; i++){
    var tempArr = infoArr[i].split('=');
    if(tempArr[0]){
       obj[tempArr[0]] = tempArr[1];
    }
}
```

## try...catch 异常捕获机制

```js
/*
如果没有try catch,那么当程序中有错误时,程序就会停到错误的位置,不在继续往下执行,即使后面的代码是正确的也不执行,那么这样的用户体验不好,所以我们可以使用try catch异常捕获机制,将可能有问题的代码放在try中,然后将解决方式放在catch中.这样就算程序发现错误,程序也会继续执行后面的代码.
1. 格式
try{
	可能会有问题的代码
}catch(error){
	错误的处理方式
}

*/
```

## 函数

```js
/*
当局部变量与全局变量名相同时,要使用全局变量可以用window.变量名或this.变量名调用

arguments对象: 该对象是函数内部的一个对象,即该对象只能在函数内部使用,不能在外部使用.它的作用是用来管理函数被调用时传递过来的实参.它不是一个数组,它是一个伪数组.在管理实参时也是用下标的方式对实参进行编号,即可以使用arguments[下标]的形式操作实参.
形参和arguments的关系: 形参和arguments都可以管理实参,并且它们管理的是同一份数据.在操作实参时可以用形参,也可以用arguments,为了方便通常使用形参.
如果实参的个数是确定的,那么我们就定义形参,如果实参的个数是不确定的时候,就不定义形参.用arugments来操作实参

arguments对象的两个属性 length callee
length属性: 获取实参的个数
callee属性: 获取arguments对象所在的函数,即callee属性指向了arguments对象所在的函数.常与递归函数结合使用或与匿名自执行函数结合使用.

1. 重载函数: 重载函数就是指两个函数的名称相同,但是它们的形参个数不同或形参的类型不同
注意: JavaScript中没有重载函数,在JavaScript中如果函数名称相同那么后面的函数会覆盖前面的函数
如果要在JavaScript中模拟重载函数,可以使用arguments对象来实现

2. 递归函数: 指在一个函数内部调用了自己的函数 
注意: 在使用递归函数时一定要确定递归函数的"出口",即在某个时刻能够让函数不再调用自己
eg:
function fun1(n){
	if(n == 1){
		return 1;
	}else{
		return arguments.callee(n-1) + n;
	}
}

3. 匿名函数: 没有函数名称的函数,匿名函数可以和事件相结合,常用格式如下:
HTML元素.on事件名称 = function(){...}

4. 回调函数: 如果一个函数被当做一个函数的参数,那么这个被作为参数的函数就是回调函数 
回调函数常用匿名函数

5. 匿名自执行函数: 没有名称且不需要手动调用的函数
格式:
1) 无参无返回值的匿名自执行函数
(function(){
	函数体
})();

2) 有参无返回值的匿名自执行函数
(function(形参1, 形参2, ...){
	函数体
})(实参1, 实参2, ...)

3) 有参有返回值的匿名自执行函数
var res = (function(形参1, 形参2, ...){
	函数体
	return data;
})(实参1, 实参2, ...);
注意: 匿名自执行函数通常是用来创建块级作用域

*/
```

## setInterval()/clearInterval()

```js
/*
1. setInterval()方法
作用: 用来设置定时器,能够在一定的时间间隔下重复执行某个操作
格式: window.setInterval(要重复执行的操作, 时间间隔);
参数说明: 
	要重复执行的操作: 可以是匿名函数,也可以是有名函数的名称
	时间间隔: 以毫秒作为单位
返回值: 返回值为一个数值,这个数值就是该定时器的编号,可以用来删除该定时器
	
2. clearInterval()方法
作用: 清除定时器,即停止setInterval方法的执行
格式: window.clearInterval(定时器编号);

*/
```

## DOM

### DOM文档的加载顺序

```js
/*
1. 解析HTML结构
2. 加载外部脚本和样式表文件
3. 解析并执行脚本代码
4. DOM树构建完成 ==> DOMContentLoaded事件执行
5. 加载图片等外部文件
6. 页面加载完毕 ==> load事件执行

*/
```

### DOM节点及样式表属性的操作

```js
/*
1. nodeType属性: 获取节点类型
元素节点: 1
属性节点: 2
文本节点: 3
注释节点: 8
文档节点: 9
nodeName属性: 获取节点名称
元素节点: 元素名称/标签名
属性节点: 属性名称
文本节点: #text
注释节点: #comment
文档节点: #document
nodeValue属性: 获取节点值
元素节点: null
属性节点: 属性值
文本节点: 文本内容
注释节点: 注释内容
文档节点: null

2. 注意: querySelector获取的是静态的元素,而getElementBy..获取的是动态的元素(动态: 通过js方式添加页面的元素)

3. 页面节点中常见的关系:
//不常用 获取有问题 容易拿到空白文本节点
1) childNodes: 父元素的所有子节点(包含换行)
2) firstChild: 父元素的第一个子节点(包含换行)
3) lastChild: 父元素的最后一个子节点(包含换行)
4) parentNode: 父节点
5) nextSibling: 下一个兄弟节点(包含换行)
6) previousSibling: 前一个兄弟节点(包含换行)
//常用 不存在空白文本节点 作用同上
1) children
2) firstElementChild
3) lastElementChild
4) parentElement
5) nextElementSibling
6) previousElementSibling

4. 页面中特殊节点的获取
1) 获取HTML节点: document.documentElement
2) 获取body节点: document.body
3) 获取head节点: document.head
4) 获取或设置title节点: document.title 或 document.title = '值'
5) 获取文档节点: document 或者 document.body.ownerDocument(也可以使用元素节点的ownerDocument属性来获取文档节点)
6) 获取文档类型声明: document.doctype

document对象的属性:
1) documentURI: HTML文档地址
2) URL: HTML文档地址
3) domain: 返回地址中的域名部分
4) lastModified: 返回文档上一次修改的时间
5) location: 返回location对象 该对象用来操作url地址,包含如下属性和方法:
	href: 获取或设置当前地址 能够利用它实现页面的跳转 eg: document.location.href == '地址'
	assign:  设置url地址 eg: document.location.assign('地址')
	注意: href属性和assign方法在实现页面跳转时都会产生浏览记录,如果要实现页面跳转还可以使用window对象的location属性来进行跳转. eg: window.location = '地址'
6) readyState属性: 返回的是页面加载的状态,包含三种状态
	loading: 表示正在加载HTML文档,并解析
	interactive: 表示正在加载外部资源
	complete: 表示整个文档加载完毕
7) anchors: 获取页面中所有的具有name属性的超链接
8) forms: 获取页面中的所有的form节点
9) images: 获取页面中的所有的img节点
10) links: 获取页面中带有href属性的超链接
11) scripts: 获取页面中的所有script节点

DOM操作CSS行内样式(只适用于行内样式 外部样式获取不到)
ele.style.cssText //获取行内元素style属性字符串 一般不用该属性赋值 会重置原行内样式
ele.style.fontSize //获取或修改带有"-"连接的属性时使用驼峰命名法

行内样式表对象的方法 不需要使用驼峰命名法
ele.style.setProperty(propertyName, value); //设置某个CSS属性
ele.style.getPropertyValue(propertyName); //读取某个CSS属性的值
ele.style.removeProperty(propertyName); //删除某个CSS属性

getComputedStyle方法
作用: 可以在谷歌浏览器(包含火狐等其他浏览器,不包含低版本的IE浏览器)获取或设置外部样式表或内部样式表
格式: window.getComputedStyle(ele, null)
返回值: 返回经过计算的元素身上的样式

低版本的IE浏览器获取内部或外部样式表,可以使用currentStyle属性
格式: ele.currentStyle
返回值: 返回样式表对象

获取内部样式或外部样式的兼容写法
function getStyle(ele, cssName){
	if(window.getComputedStyle == undefined){//IE浏览器
		return ele.currentStyle[cssName];
	}else{
		return window.getComputedStyle(ele, null)[cssName];
	}
}

*/
```

### DOM常用方法

```js
/*
appendChild()方法
作用: 在父元素末尾插入新节点
格式: 父节点.appendChild(新节点)
注意: 具有移动节点的功能(父元素中有该子节点,通过该方法将该子节点移动到父元素末尾)

insertBefore()方法
作用: 将某个节点插入到目标节点前面
格式: 父节点.insertBefore(要插入的新节点, 目标节点)

removeChild()方法
作用: 删除节点
格式: 父节点.removeChild(要被删除的节点)
返回值: 被删除的元素
注意: 被删除的元素没有消失,放在内存中 一般通过返回值获取到被删除的元素再添加进来

replaceChild()方法
作用: 替换某个节点
格式: 父节点.replaceChild(新的节点, 旧的节点)
返回值: 被替换掉的节点

isEqualNode()方法
作用: 判断两个节点是否相等
格式: 节点1.isEqualNode(节点2)
返回值: true false

contains()方法
作用: 判断某个节点是否包含另外的某个指定的节点
格式: 节点1.contaions(可能包含的节点)
返回值: true false

hasChildNodes()方法
作用: 判断是否有子节点
格式: 节点.hasChildNodes()
返回值: true(表示该元素不是一个空元素) false(表示该元素是一个空元素) 

*/
```

### DOM常用属性

```js
/*
offsetParent属性: 返回的是样式偏移时的参照物
1) 如果元素没有父元素,那么返回的是body
2) 如果元素有父元素,但是父元素没有定位,那么返回的是body
3) 如果元素有父元素且父元素有定位,那么返回的是具有定位且离该元素最近的父元素

offsetTop属性: 距离偏移对象顶部的距离
offsetLeft属性: 距离偏移对象左侧的距离
格式: 元素节点.offsetTop

offsetWidth属性: 返回元素的宽度(包括元素宽度、内边距和边框，不包括外边距和滚动条)
offsetHeight属性: 返回元素的高度(包括元素高度、内边距和边框，不包括外边距和滚动条)
clientWidth属性: 返回元素的宽度(包括元素的宽度、内边距和滚动条，不包括外边距和边框)
clientHeight属性: 返回元素的高度(包括元素的高度、内边距和滚动条，不包括外边距和边框)
注意: 
1) 如果要获取页面视口的宽度和高度,那么推荐用clientWidth和ClientHeight,如果要获取元素的宽度和高度推荐用offsetWidth和offsetHeight
2) 如果要获取页面石窟的宽度和高度,需要兼容浏览器
视口宽度: var viewWidth = document.documentElement.clientWidth || document.body.clientWidth;

*/
```

### JavaScript中事件的常用添加方法

```js
/*
1. 行内添加事件
<div onclick='fn(this)'></div> //this指向问题,传入一个实参this,代表了当前事件所应用到的元素
<div onclick='fn1();fn2()'></div> //div绑定了两个事件fn1和fn2,不会被覆盖掉
<div onclick='fn1()' onclick='fn2()'></div> //事件fn2()会被屏蔽掉

2. DOM0级事件处理程序
添加方式: 元素节点.on事件名 = function(){
	函数体
};
this指向问题: 在事件处理函数中直接使用this,这个this就代表了当前事件所应用到的元素
删除方式: 元素节点.on事件名 = null;
注意: 
	如果一个元素身上通过DOM0级事件处理程序添加了多个相同的事件,那么这些事件会被覆盖掉,只会绑定最后一次添加的事件

3. DOM2级事件处理程序
添加方式: 元素节点.addEventListener(参数1, 参数2, 参数3);
参数说明:
	参数1: 表示事件名称
	参数2: 表示事件处理函数,可以是匿名函数,也可以是有名函数的名称
	参数3: 表示事件流,值为true(事件捕获)、false(默认值,事件冒泡)
删除方式: 元素节点.removeEventListener(参数1, 参数2, 参数3) 参数类型同上,如果是事件要被删除,那么在添加事件时参数2不可以是匿名函数,只能是函数名称
注意: 
	DOM2级事件处理程序不适用于IE8及以前的浏览器版本
	如果一个元素身上通过DOM2级事件处理程序添加了多个相同的事件,那么这些事件可以同时存在
DOM2级事件处理程序中如何使用this: 在事件处理函数中直接使用this,这个this就代表了当前事件所应用到的元素
eg: 
	ele.addEventListener('click', fn1, false);
	
事件流: 所谓事件流就是页面中事件的执行顺序.可以分为两部分: 事件冒泡、事件捕获
事件冒泡: 从当前元素开始逐步向外扩展
事件捕获: 从根节点开始逐步向当前元素扩展
	
*/

//定义一个函数,该函数的功能是为元素添加事件(解决DOM2级事件处理程序在IE下不支持的问题)
/*
	ele: 表示要被添加事件的元素
	eventName: 表示事件的名称
	callback: 表示事件触发时要执行的操作
	eventStream: 表示事件流
*/
function addEvent(ele, eventName, callback, eventStream){
    if(ele.addEventListener == undefined){//IE11以下不支持addEventListener(IE11支持)
        ele.attachEvent('on'+eventName, callback);
    }else{
    	ele.addEventListener(eventName, callback, eventStream)       
    }
}

//定义一个函数,该函数的功能是为元素删除事件(解决DOM2级事件处理程序在IE下不支持的问题)
/*
	ele: 表示要被删除事件的元素
	eventName: 表示事件的名称
	callback: 表示事件触发时要执行的操作
	eventStream: 表示事件流
*/
function removeEvent(ele, eventName, callback, eventStream){
    if(ele.removeEventListener == undefined){//IE11以下不支持removeEventListener(IE11支持)
       ele.detachEvent('on'+eventName, callback);
   	}else{
        ele.removeEventListener(eventName, callback, eventStream);
    }
}

```

### 事件对象

```js
/*
事件对象: 事件对象是JavaScript中的一个内置对象,该对象记录了和当时事件相关的信息,另外事件对象也提供了大量的属性和方法帮助我们操作事件
1. 事件对象的获取:
	1) 谷歌浏览器: 事件对象被以实参的形式传递给事件处理函数
	2) IE8及以前的低版本的IE浏览器: 可以使用window对象的event属性来获取

2. 事件对象的常用属性:
1) type: 获取当前事件的类型
2) altKey、shiftKey、ctrlKey: 这三个属性的作用是判断是否按了键盘上的alt、shift、ctrl键,如果按了则返回true,否则返回false
3) keyCode: 作用是当键盘事件被触发时,该属性可以用来获取被按下去的按键的键码值(ASCII码)
4) screenX、screenY: 获取鼠标点击的点距离屏幕左侧和顶端的距离
5) clientX、clientY: 获取鼠标点击的点距离视口的左侧和顶端的距离,不受滚动条的影响
6) pageX、pageY: 获取鼠标点击的点距离页面左侧和顶端的距离,受滚动条的影响
7) offsetX、offsetY: 获取鼠标点击的点距离元素自身左侧和顶端的距离
8) currentTarget: 表示当前谁身上的事件正在被触发
9) target: 获取当前哪个元素被点击了 (IE8及以下使用的是srcElement属性)
10) bubbles: 判断当前事件是否支持事件冒泡,返回值为true false
11) eventPhase: 该属性值为1、2、3
	1: 表示由于事件捕获而引起的事件的执行
	2: 表示事件流中的当前元素
	3: 表示由于事件冒泡而引起的事件的执行
12) button: 判断点击了鼠标的哪个按钮
	0: 表示左键
	1: 表示滚轮
	2: 表示右键
13) wheelDelta: 表示滚轮滚动的方向 上滚: 148 (120) 下滚: -148 (-120) 各个浏览器值可能不同

3. 事件对象的常用方法:
1) preventDefault(): 取消默认行为 (IE8及以下使用的是returnValue = false来取消默认行为) eg: 超链接的跳转
2) stopPropagation(): 阻止事件冒泡 (IE8及以下使用的是cancelBubble = true来取消事件冒泡)

*/

//获取事件对象的兼容写法
div.onclick = function(e){
    e = e || window.event;
}

//点击鼠标右键时触发 (取消鼠标右键时的功能悬停框)
document.oncontextmenu = function(e){
    e = e || window.event;
    e.preventDefault == undefined ? e.returnValue=false : e.preventDefault();
}

//拖动元素
<div id='box' style="width: 200px;height: 200px;background-color: red;position: fixed;"></div>
var div = document.querySelector('#box');
//为div添加鼠标按下事件
div.onmousedown = function(e){
    e = e || window.event;
    //获取鼠标点击的点距离自身左侧和顶端的距离
    var div_x = e.offsetX;
    var div_y = e.offsetY;
    //为document对象添加鼠标移动事件
    document.onmousemove = function(e){
        e = e || window.event;
        //获取鼠标移动的点距离视口左侧和顶端的距离
        var body_x = e.clintX;
        var body_y = e.clientY;
        //设置div的left和top的值(给div设置position)
        div.style.left = (body_x - div_x) + 'px';
        div.style.top = (body_y - div_y) + 'px';
    }
}
//为div设置鼠标松开的事件
div.onmouseup = function(){
    document.onmousemove = null;
}

```

### 常用事件

```js
/*
1. 鼠标事件
click事件: 鼠标单击事件
dblclick事件: 鼠标双击事件
mouseover事件: 如果有后代元素,那么在进入到后代元素或者从后代元素再进入到自身时会多次触发该事件
mouseout事件: 如果有后代元素,那么在进入到后代元素或者从后代元素再进入到自身时会多次触发该事件
mouseenter事件: 如果有后代元素,不会重复触发
mouseleave事件: 如果有后代元素,不会重复触发
mousedown事件: 在鼠标压下去的时候只触发一次,不会持续触发
mouseup事件: 在鼠标松开的时候触发
mousemove事件: 在鼠标移动的时候触发,会持续触发
mousewheel事件: 鼠标滚轮事件,其事件对象中的button属性值为0  注意: 不兼容火狐浏览器
	适用于火狐浏览器的鼠标滚轮事件: DOMMouseScroll事件 注意: 需要使用DOM2级事件处理程序的添加方式来添加
	该事件的事件对象中有detail属性,用来判断滚轮滚动的方法,如果是正数表示向下,负数表示向上

2. 表单事件
focus事件: 获取焦点时触发
blur事件: 失去焦点时触发
input事件: 当表单元素中的内容变化就触发
change事件: 当失去焦点的时候才会触发(前提是输入框中的内容有变化)
submit事件: 提交表单元素时触发,该事件可以用来阻断数据的提交,如果该事件对应的事件处理函数的返回值为false就会阻断提交  注意该事件是给form元素加
reset事件: 当重置按钮被点击时触发  注意该事件是给form元素加

3. 键盘事件
keydown事件: 按下任意键都可以触发该事件  按下不放,事件会被连续触发
keypress事件: 按下任意键都可以触发该事件(功能键除外)  按下不放,事件会被连续触发
keyup事件: 释放按键时触发

4. 滚动条事件
scroll事件: 当拉动滚动条时触发该事件 会持续触发 如果给窗口加该事件: window.onscroll = function(){...}
常用的属性(元素的属性): scrollTop/scrollLeft
scrollTop: 该属性的作用是用来设置或者获取在拉动滚动条时被卷上去的内容的高度 结果为数值
scrollLeft: 该属性的作用是用来设置或者获取在拉动滚动条时被卷到左侧的内容的宽度 结果为数值
注意: 在拉动窗口的滚动条时,如果要获取scrollTop或scrollLeft,不可以使用window.scrollTop或window.scrollLeft,因为window对象没有这两个属性,需要在document.documentElement或者document.body对象中去获取
eg: var scrollTop = document.documentElement.scrollTop || document.body.scrollTop;

5. 移动端事件
touchstart事件: 当手指触摸到屏幕或指定元素时触发
touchmove事件: 当手指在屏幕或指定元素上移动时触发
touchend事件: 当手指从屏幕离开时触发
touchcancel事件: 当系统停止跟踪触摸时触发 (例如电话接入或弹出信息)
移动端事件对象中常用的属性:
touches: 该属性中主要保存放到屏幕上的所有触摸点的相关信息 (一个或多个手指触摸,只记录手指按下) 
targetTouches: 该属性主要保存了和当前元素相关的触摸点信息 (一个或多个手指触摸,只记录手指按下)
changedTouches: 该属性主要保存了由触摸点变化形成的信息 (手指按下和离开时都有记录)

6. 文档事件
load事件: 当文档中所有节点都加载完毕后触发该事件 如文档的所有图片加载完 通常该事件是给window对象添加的
DOMContentLoaded事件: 该事件和load事件类似,但是该事件的触发事件早于load事件,因为该事件会在DOM树渲染完毕后触发,而load事件只有在整个文档加载完毕后触发 注意: 该事件只能用DOM2级事件处理程序添加事件
readystatechange事件: 文档加载状态判断事件 (即document.readyState值发生改变时触发 属性值: loading(加载DOM中) interactive(加载外部资源) complete(加载完成))


*/

//兼容火狐的滚轮事件
function gd(e){
    e = e || window.event;
    var direction = 0;//滚动方向
    if(e.wheelDelta){//有值
       direction = e.wheelDelta>0 ? 1 : -1;
    }else{//火狐
       direction = e.detail<0 ? 1 : -1;
    }
}
ele.onmousewheel = gd; //谷歌
ele.addEventListener('DOMMouseScroll', gd, false);//火狐
```

### 事件委托

```js
/*
事件委托也被称为事件代理,就是指将事件委托给祖先元素,然后利用事件冒泡机制和事件对象让该祖先元素下面的所有后代元素可以具有同一类型的事件
好处: 如果是用普通的方式给每个子元素加事件使用的是querySelectorAll方法,不能获取动态js添加的子元素,使用事件委托就可以避免这种情况(事件是加在祖先元素上的)

*/
```

## BOM

```js
/*
BOM: Browser Object Model浏览器对象模型,它不是一个对象,可以说是一个对象的集合.它里面有很多对象,利用这些对象可以操作浏览器即浏览器中的内容.主要包含如下对象: window、location(浏览器当前URL信息)、history(浏览器访问历史信息)、screen(客户端屏幕信息)、navigator(浏览器本身信息)、document(文档对象)等.在众多属性中window属性是BOM中的顶级属性,其他对象都是window对象的属性,只不过本身也是对象类型

*/
```

### window对象 (global)

```js
/*
1. 定义:
1) window对象是BOM中的顶级对象,其他对象是window对象的一个属性.
2) window对象也是一个全局对象,因为在全局作用域下面定义的所有的变量、方法都相当于给window对象绑定属性和方法,可以使用window.的形式来使用这些属性和方法.在平时使用时可以将window.省略.
3) 如果是全局的变量或方法,还可以使用this.的形式来调用,因为在全局环境下window === this
4) window对象不需要手动创建,当浏览器窗口被打开时,后台会自动创建一个用来管理当前窗口的window对象.当浏览器窗口被关闭时该对象会被自动销毁

2. window对象常用方法:
1) alert(): 弹出警告框 不解析标签  支持转义字符
2) confirm(): 弹出确认框 返回值为true或false
3) prompt(): 弹出输入框
4) isNaN(): 判断参数是否是NaN 返回值为true表示是NaN,否则不是NaN
5) isFinite(): 判断参数是否为有限数值 返回值为true表示是有限,否则不是有限
6) open():
	作用: 打开新窗口
	格式: window.open('地址', '窗口名称', '窗口特性'),三个参数都可以省略,如果省略表示打开一个空白窗口
	参数说明:
		地址: 新窗口网站地址
		窗口名称: 窗口名称可以不写,如果不写,那么会多次打开新窗口.如果写,那么会打开一次新窗口,后面在执行open方法时会在上一次打开的窗口里面重新加载页面
		窗口特性: eg: 'width=200 height=300 left=300 top=300'
	返回值: 返回值是代表新窗口的window对象
7) close():
	作用: 关闭当前窗口
	格式: window.close()
8) setInterval()/clearInterval(): 用来设置定时器,能够在一定的时间间隔下重复执行某个操作 / 清除该方法
9) setTimeout()/clearTimeout(): 在指定的延迟时间后来执行代码 / 清除该方法
10) focus(): 把键盘焦点给予一个窗口
11) blur(): 把键盘焦点从顶层窗口移开
12) moveBy、moveTo、resizeTo、resizeBy、scrollBy、scrollTo ...
	
3. window对象常用属性:
1) name: 默认值为空字符串,该属性可以用来在不同窗口间进行数据的传递 (原理: 通过a标签跳转到新地址,新地址中给window.name赋值,再回退到原页面,原页面中的window的name就会有值  两个页面使用的是一个window)
2) screenX: 获取浏览器窗口距离屏幕左侧的距离
   screenY: 获取浏览器窗口距离屏幕顶端的距离
3) outerHeight: 设置或返回一个窗口的外部高度,包括所有界面元素(如工具栏/滚动条)
   outerWidth: 设置或返回一个窗口的外部宽度,包括所有界面元素(如工具栏/滚动条)
4) innerHeight: 返回窗口的文档显示区的高度 (适用于移动端获取视口的高度)
   innerWidth: 返回窗口的文档显示区的宽度 (适用于移动端获取视口的宽度)
   
*/
```

### Location对象

```js
/*
常用属性:
1. hostname: 返回web主机的域名
2. pathname: 返回当前页面的路径和文件名
3. port: 返回web主机的端口
4. protocol: 返回所使用的web协议(http: 或 https:)
5. search: 是一个可读可写的字符串,可设置或返回当前url的查询部分(获取的是从?之后的部分,包含?)
	用来获取向服务器请求时的参数字符串

*/
```

### navagator对象

```js
/*
常用属性:
1. appCodeName: 浏览器代码名的字符串表示
2. appName: 官方浏览器名的字符串表示
3. appVersion: 浏览器版本信息的字符串表示
4. userAgent: 返回和浏览器内核相关的信息
5. cookieEnabled: 如果启用cookie返回true,否则返回false
6. javaEnabled: 如果启用java返回true,否则返回false
7. platform: 浏览器所在计算机平台的字符串表示

*/

eg: 如果window.navigator.userAgent的返回值中出现了Mobile,可以确定用户使用的是移动设备
```

history对象

```js
/*
常用方法:
1. back(): 跳转到栈中的上一个页面
2. forward(): 跳转到栈中的下一个页面
3. go(num): 跳转到栈中的指定页面

*/
```

## script

```js
/*
script默认的加载顺序是从上到下加载中
script标签的属性:
defer: 延迟加载,等DOM节点都加载完后再加载 属性值和属性名相同
async: DOM加载和js脚本加载异步执行,同时进行
	优势: 避免了因DOM文件过大导致的文件加载阻塞
	缺陷: 无法确定js脚本到底何时执行,并仅对外部js脚本生效

*/
```

## 浏览器性能优化

```js
/*
回流(重排): 当render tree中的一部分(或全部),因为元素的规模尺寸、布局、隐藏等改变而需要重新构建 每个页面至少有一次回流(即页面在第一次加载的时候)
重绘: 当render tree中的一些元素需要更新属性,而这些属性只是影响元素的外观、风格,而不会影响布局的,比如color ...
注意: 回流必将引起重绘,而重绘不一定会引起回流

引起回流和重绘的原因:
1) 页面初始渲染
2) 改变字体,改变元素尺寸(宽、高、内外边距、边框、改变元素位置等)
3) 改变元素内容 (文本或图片或用户在input框中输入文字)
4) 添加或删除可见DOM元素 (如果是删除本身就存在display:none的元素不会发生回流visibility:hidden的元素显示或隐藏不影响回流)
5) fixed定位的元素,在拖动滚动条的时候回一直回流
6) 调整窗口大小
7) 计算offsetWidth和offsetHeight属性	

如何从回流和重绘方面提高浏览器性能
1) 不要一项一项去修改样式,尽可能一口气写完(可以写在一起,不要被打断),最好使用style.cssText
2) 读写DOM尽量放在一起
3) 使用文档碎片 document.createDocumentFragment()
4) 使用fixed或absolute可以减少回流和重绘

documentFragment (文档碎片)
nodeType的值为11,nodeName的值为#document-fragment
1) documentFragment是一种文档片段,一种'轻量级节点'
2) 通常作为仓库来使用,不存放在DOM树上,是一种游离态
用途:
当使用js添加多个节点时,节点加入到DOM树上时,节点需要一个个渲染,这样节点数较多时就会影响浏览器的渲染效率
可以将创建的节点都放在documentFragment这样的节点上,然后把documentFragment加入到DOM,只需要完成一次渲染就可以达到之前渲染很多次的效果

*/
```

## call和apply

```js
/*
call和apply都是用来扩展函数的作用域范围
1. call的格式: 函数.call(借用者, 参数1, 参数2, ...)
2. apply的格式: 函数.apply(借用者, [参数1, 参数2, ...])
3. 说明: call和apply方法是函数对象的两个方法 利用这两个方法来扩展函数的作用域时,借用过来的函数不再需要手动调用

*/
```

## 正则表达式

```js
/*
定义: 正则表达式也被称为规则表达式,它是由一些普通字符和特殊字符(也称为元字符)构成的表达式.
作用: 用来验证字符串是否符合格式要求,或者判断字符串中是否包含指定格式的子串

1. 字面量形式创建正则表达式: var 正则表达式名称 = /表达式内容/修饰符

2. 利用构造方法创建正则表达式: var 正则表达式名称 = new RegExp('表达式内容', '修饰符');
修饰符:
i: 表示忽略大小写
g: 表示全局匹配
ig: 表示即忽略大小写也全局匹配

3. test方法
1) 作用: 用来判断字符串是否符合正则表达式的格式要求,如果符合要求返回true,否则返回false
2) 格式: 正则表达式.test(字符串);

4. 正则表达式的构成: 普通字符、特殊字符
1) 普通字符: 字母、数字、_(下划线)
2) 特殊字符(元字符):
	① 定位符:
	^: 表示以某个字符开头
	$: 表示以某个字符结尾
	注意: 如果正则表达式中既有^又有$,那么在匹配时无论是内容还是字符的个数都要匹配
	② 表示数量的限定符:
	*: 表示它前面的字符个数为0到无穷多个
	+: 表示它前面的字符个数为1到无穷多个
	?: 表示它前面的字符个数为0到1个
	{n}: 表示它前面的字符个数只能是n个
	{n,m}: 表示它前面的字符个数为n-m个
	{n,}: 表示它前面的字符个数为n到无穷多个
	③ 转义字符: 转义字符就是指在普通字符前面加反斜线,使它具有特定的功能和含义.也可以在具有特定功能和含义的字符前加反斜线,将它转化为普通字符,如\d表示任意一个数字,如\/表示将正则表达式中的斜线转换为普通的斜线
	\d: 表示任意一个数字
	\D: 表示任意一个非数字
	\w: 表示任意一个字母、数字、下划线
	\W: 表示任意一个非字母、数字、下划线
	\s: 表示任意一个空白符,如空格、制表符(Tab键)
	\S: 表示任意一个非空白符
	④ 备选字符集
	[值1值2值3值4]: 中括号里面的值表示字符串中可以匹配到的任意一个值
	[值1-值n]: 表示值1到值n键的任意一个值为备选选项
	[^值1值2值3]: 表示字符串中不可以包含中括号里面的任意一个值
	[\u4e00-\u9fa5]: 表示任意一个汉字
	⑤ 分组和选择
	(): 表示分组
	|: 表示或的意思
	⑥ 其他
	.: 点表示除了\n之外的任何字符
	\b: 匹配单词边界 注意: 所谓单词就是指字母、数字、下划线构成的连续字符
	\B: 匹配单词的非边界
	
5. exec方法
作用: 该方法是正则表达式对象的一个方法,可以利用这个方法在字符串中检索是否有和该正则表达式匹配的子串,如果有则返回,类似于match方法
格式: 正则表达式.exec(字符串);
注意: 该方法即使加上全局匹配的修饰符也是最多只返回一个匹配的字符,想要全局匹配就需要多次调用该方法 每次调用该方法后该方法对应的指针指向的就是上次匹配的字符索引的下一个位置,依次类推,直到返回null时,指针重新指向字符串索引为0处

6. 贪婪模式和懒惰模式
贪婪模式: 如果正则表达式中有表示数量的特殊字符,如*、+、{n,m}等,在匹配时会尽可能多的匹配字符,默认
懒惰模式: 如果正则表达式中有表示数量的特殊字符,如*、+、{n,m}等,在匹配时会尽可能少的匹配字符
注意: 如果要将贪婪模式改为懒惰模式,只需要在数量词后面加上?即可
	

*/

eg: 将字符串str转换为数组,以数字作为分隔符
var str = 'he2ll3ow4or1ld';
var arr = str.split(/\d/); // str.split(/[0-9]/) 也可以实现
console.log(arr);

注意: 字符串的search方法在匹配到第一个字符串后就停止匹配
```

## hash表去重

```js
/*
原理: 将已经出现过的元素当做属性名,存入一个对象中,下标的引用要比用indexOf搜索数组快的多
缺点: 内存占用很多,以牺牲空间换取时间

*/
eg: 
var arr = [1,2,1,3,2,4,4,5,4,2,3];
var newArr = [];
var obj = {};
for(var i=0; i<arr.length; i++){
    if(!obj[arr[i]]){
       newArr.push(arr[i]);
       obj[arr[i]] = 888;    
    }
}
```

## 冒泡排序

```js
/*
升序
特点: 进行数组长度-1轮次 每轮结束会依次在数组末尾生成一个最大数 第二大数 ... 依次向前排列
每轮结束后生成的最大数不参与下轮的比较

*/
eg: 
var arr = [3, 22, 32, 43, 1, 11, 12, 234, 35];
for (var i = 0; i < arr.length - 1; i++) {
    for (var j = 1; j < arr.length - i; j++) {
        if (arr[j - 1] > arr[j]) {
            var temp = arr[j - 1];
            arr[j - 1] = arr[j];
            arr[j] = temp;
        }
    }
}
```

## 快速排序

```js
/*
特点: 在数组中随机选择一个中间值,将大于中间值的元素放在右边,小于中间值的元素放在右边
使用递归调用

*/
eg: 
var arr = [3, 22, 32, 43, 1, 11, 12, 234, 35];
function quickSort(myArr){
    //判断数组的长度是否是0或1,如果是直接返回该数组
    if(myArr.length <= 1){
       return myArr;
    }
    //获取数组中基准值的下标
    var index = Math.floor(myArr.length / 2);
    //根据下标获取中间值,并删除中间值
    var midValue = myArr.splice(index, 1)[0];
    //定义两个空数组用来接收比中间值小和比中间值大的数
    var left = [];
    var right = [];
    //遍历数组,用数组中的剩余元素和中间值比较,如果比中间值小存放在left中,否则存放在right中
    for(var i=0; i<myArr.length; i++){
        if(myArr[i] < midValue){
           left.push(myArr[i]);
        }else{
            right.push(myArr[i]);
        }
    }
    return quickSort(left).concat([midValue], quickSort(right));
}
var newArr = quickSort(arr);
```

## 二分查找法

```js
/*
使用二分查找法,必须保证数组是有序的

*/
eg:
var arr = [1,2,3,4,5,6,7,8,9,12,15,17,111];
//利用二分查找法,在数组中查找指定元素,将数组元素的下标返回
function checkIndex(myArr, value) {
    //定义数组的开始和结束索引
    var beginIndex = 0;
    var endIndex = myArr.length - 1;
    while (beginIndex <= endIndex) {
        //获取中间值的索引
        var midIndex = parseInt((beginIndex + endIndex) / 2);
        if (value == myArr[midIndex]) {
            return midIndex;
        } else if (value < myArr[midIndex]) {
            endIndex = midIndex - 1;
        } else if (value > myArr[midIndex]) {
            beginIndex = midIndex + 1;
        }
    }
    return -1;//数组中没有找到该元素
}
var valueIndex = checkIndex(arr, 3);
```

## JSON

```js
/*
1. JSON: JSON是JavaScript Object Notation的缩写,它是一种数据格式.JSON的本质是一个字符串.

2. JSON中的构成元素: 简单值、对象、数组
1) 简单值: 数值型、字符型、布尔型、Null,注意没有undefined
2) 对象: 用来存储无序的属性,注意对象不可以有名称,也不可以以分号作为结尾,没有函数
3) 数组: 用来存储有序的数据,注意数组也不可以有名称,也不可以以分号结尾

3. 注意:
1) JSON中对象的键值对,键必须用双引号包起来
2) JSON中的字符串必须用双引号包起来

4. JSON对象的书写位置
1) 可以写在独立的JSON文件中,文件的拓展名为.json
2) 将JSON写在js文档中

5. JSON字符串与JS对象之间的相互转化
1) parse方法: 将JSON字符串转换为JS对象 格式: window.JSON.parse('JSON字符串')
2) stringify方法: 将JS对象转换为JSON字符串 格式: window.JSON.stringify(js对象)

*/
```

## 面向对象

```js
/*
1. 对象: 指具有特定功能的无序的属性和方法的集合
2. 如何创建对象: 字面量形式、构造方法
3. 自定义构造方法
function 构造方法名称(形参1, 形参2){
	this.属性1 = 形参1;
	this.属性2 = 形参2;
	this.方法1 = function(){}
	this.方法2 = function(){}
}
var obj = new 构造方法名称(实参1, 实参2);//调用构造方法
构造方法在执行时的流程:
1) 如果有形参,那么现将实参的数据传递给构造函数的形参.并创建一个空对象,让this指向这个空对象
2) 执行构造函数的语句,为空对象(this)绑定属性并初始化
3) 将创建好的对象返回给外部

4. 构造方法中的变量可以通过函数来操作
function Student(age){
	var sign = 1;
	this.age = age;
	this.getSign = function(){
		return sign;
	}
}

5. 静态属性和静态方法
定义: 给构造方法直接绑定属性和方法
作用: 一般是用来检测构造方法的变化
注意: 只能用构造函数来调用
eg: 
Student.a = '静态属性';
Student.fn = function(){console.log('静态方法')};
var str = Student.a;//静态属性的调用
Student.fn();//静态方法的调用

6. 构造方法在使用时的注意事项
1) 构造方法的名称的首字母大写,目的是和普通方法做区分
2) 构造方法的名称代表了对象的类型
3) 调用时必须要加new
4) 构造方法中为对象绑定的属性为私有属性,即通过该构造方法创建对象时,每个对象都会有一份属性,并且这些属性互不干扰

7. 构造方法的不足
如果将所有的属性和方法都封装到构造方法中,那么当其属性值相同时,势必造成内存资源的浪费(因为构造方法里面的所有东西,会在创建对象时给每个对象身上绑定一份这样的属性).
解决: 将属性值相同的内容存放到'公共空间' -- 原型

8. instanceof操作符
作用: 判断某个引用类型的数据的具体类型
格式: 数据 instanceof 类型
返回值: 如果属于该类型则返回true,否则返回false

9. hasOwnProperty方法
作用: 判断某个属性是否为对象的私有属性
格式: 对象.hasOwnProperty('属性名称');
返回值: 如果是则返回true,否则返回false

10. in关键字 (for...in 用来遍历对象的属性)
作用: 判断对象是否有某个属性(不论是公有还是私有的)
格式: '属性名称' in 对象名称
返回值: 如果是则返回true,否则返回false

*/
```

### 原型

```js
/*
1. 原型: 每个函数中都会有一个属性-prototype属性,这个属性指向了一个对象,这个对象就被称为原型对象,简称原型.原型中存储的是通过构造方法创建出来的所有对象可以共享的内容.可以使用构造方法名称.prototype属性来获取原型对象

2. 原型对象属性的操作(增删改查):
eg:
function Student(age){
	this.age = age;
}
var stu = new Student(10);
//创建原型属性
Student.prototype.country = '中国';
Student.prototype['hairColor'] = 'black';
Student.prototype.speak = function(){...};
//使用(获取或修改) 通过原型使用
var country = Student.prototype.country;
Student.prototype.country = '俄罗斯'
//使用(获取) 通过对象使用
var country = stu.country;
//删除原型中的属性
delete Student.prototype.country;

3. 为什么对象可以直接获取原型中的内容
因为每个对象的内容上有一个_proto_属性,这个属性指向了创建该对象时的原型对象.
当利用对象去查找某个属性的时候,属性的查找顺序: 先从自身的私有属性中查找,如果私有属性中有要查找的属性,则返回对应的值,如果私有属性中没有要查找的属性,则沿着_proto_的指向,到原型对象中查找,如果有则返回对应的值.
如果私有属性和原型中的属性名称相同,那么私有属性会将原型中的该属性屏蔽掉.

*/
```

### 作用域链

```js
/*
变量: 全局变量和局部变量
注意: 在函数内部,当全局变量和局部变量同名时,局部变量会将全局变量屏蔽掉,如果要使用全局变量,需要加window.或this.

作用域链: 在每个函数内部都有一个属性,这个属性是[[scope]]属性,这个属性时不可以操作的.该属性指向了一个集合,这个集合中保存了当前作用域下面变量对象(所谓变量对象是指在每个作用域下面都会有一个对象,该作用域下面定义的所有的属性和方法都是向这个对象添加的属性和方法,全局作用域下面的变量对象就是window对象)的地址,以及上级作用域下面的变量对象的地址,这个集合就是作用域链.

当在使用某个变量时,先从当前作用域下面变量对象身上查找,如果有则返回其值,如果没有则沿着作用域链向上级作用域中的变量对象身上查找,如果有则返回其值,如果没有则继续向上查找,依次类推,当找到window对象依然没有找到该变量,那么则报错.

*/
```

### 闭包

```js
/*
1. 闭包: 
1) 从广义上将被定义在其它函数内部的函数就是闭包
2) 从狭义上讲外部函数返回的持有外部函数变量的内部函数,被称为闭包
eg: 狭义上的闭包 (常用)
function fn(){
	var num = 100;
	return function(){
		console.log(num);
	};
}

2. 闭包的作用: 可以将外部函数定义的变量拿到函数外部来操作,即闭包在它所在的外部函数和全局环境间建立桥梁

3. 闭包的工作原理: 按道理说,每个函数在执行完毕后会从内存中将该函数弹出,如果函数被从内存中弹出,那么该函数的作用域链由于没有东西对它进行引用,那么这个作用域链就会被销毁,作用域链被销毁,那么该函数的变量对象也就没有被引用,变量对象也就会被销毁.闭包之所以可以在外部函数执行完毕后依然能够使用外部环境的变量,是因为当外部函数被销毁时,由于闭包中使用了外部函数的变量对象中的内容,所以外部函数的变量对象依然会被保存在内存中.

4. 闭包的不足: 由于闭包会将上级作用域下面的变量对象保存在内存中,那么如果程序中有大量的闭包,势必造成内存的资源浪费.
建议在不使用闭包的时候,手动将闭包清除.

*/
```

### 继承

```js
/*
继承就是在两个构造方法间建立起来的某种关系,通过这种关系,可以让下级构造方法创建出来的对象享用上级构造方法获取原型中的内容.
继承的方式: 借用构造方法继承、原型链继承、组合继承

1. 借用构造方法继承,格式如下:
function Person(name, age, gender){//上级构造方法
	this.name = name;
	this.age = age;
	this.gender = gender;
}
function Student(name, age, gender, subject, teacher, school){//下级构造方法
	Person.call(this, name, age, gender);//也可以使用apply方法实现借调
	this.subject = subject;
	this.teacher = teacher;
	this.school = school;
}
注意: 借用构造方法继承,继承的是上级构造方法对私有属性的绑定和初始化功能,不能继承上级构造方法原型中的内容

2. 原型链继承: 就是让下级构造方法的prototype属性指向上级构造方法创建出来的实例(对象)
格式:
function Person(){}//上级构造函数
function Student(){}//下级构造函数
Student.prototype = new Person();
Student.prototype.constructor = Student;//指回自己的构造方法
原型链: 所谓原型链就是通过原型链继承,在原型之间建立起来的一条链式结构,我们把这条链式结构称为原型链.
当对象在操作属性时,先从自身的私有属性查找,如果有则返回对应的属性值,如果没有则沿着自身的_proto_属性到它的原型中查找,如果它的原型中也没有,那么就沿着原型链继续向上查找,如果找到则返回对应值,如果找到object原型也没有对应的属性则返回undefined

如果采用原型链继承就会导致下级构造方法原型中的constructor属性的指向改变(constructor属性是原型中的一个属性,这个属性默认指向它的构造方法,如果采用原型链继承,那么constructor属性的指向就不再指向自己的构造方法,所以需要我们将它重新指回自己的构造方法)

3. 组合继承: 借用构造方法继承和原型链继承的组合,通过构造方法继承可以继承上级构造方法对私有属性的绑定和初始化功能,通过原型链继承可以继承上级构造方法原型中的内容

*/
eg: 组合继承
function Person(name, age){
    this.name = name;
    this.age = age;
}
Person.prototype.speak = function(){
    console.log('hello');
}
Person.prototype.native = '中国';
function Student(name, age, teacher, school){
    Person.call(this, name, age);
    this.teacher = teacher;
    this.school = school;
}
Student.prototype = new Person();
Student.prototype.constructor = Student;
```

## this的使用场景

```js
/*
1. 在文档中直接使用this,this代表window对象
2. 如果在全局变量或全局函数前面使用this,this代表window对象
3. 如果是HTML事件处理程序,那么将this作为事件处理函数的实参传递给事件处理函数,this代表应用事件的元素
4. 如果是DOM0级事件处理程序,事件处理函数中的this代表应用事件的元素
5. 如果是DOM2级事件处理程序,事件处理函数中的this代表应用事件的元素
6. 在字面量形式创建的对象中,如果将this放在对象方法内,这个this代表的是当前的字面量对象
7. 在构造方法中,如果将this放在属性名称前面,这个this代表的该构造方法创建出来的对象.如果将this放在某个函数中,那么这个this代表调用该函数的对象
8. 如果将this放在原型中,它代表的是使用该原型内容的对象
9. 在借用构造方法继承时,call中的this代表的是下级构造方法的对象
10. 如果在闭包中使用this,this代表window
11. 间隔调用和延迟调用: this代表window
12. 自执行函数中的this代表window

*/
```

## 设计模式

```js
/*
工厂模式: 工厂模式是JS中的一种设计模式,利用该模式可以批量创建JS对象.它的本质就是JS中的函数.
格式: 
function createStudent(name, age, teacher){
	var stu = {};
	stu.name = name;
	stu.age = age;
	stu.teacher = teacher;
	stu.speak = function(){
		console.log('hello');
	}
	return stu;
}
var s = createStudent('Tom', 15, 'Timi');
优点: 可以快速的创建对象
缺点: 不能细化对象的类型,统一都是Object类型

*/
```

