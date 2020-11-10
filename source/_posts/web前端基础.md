---
title: web前端基础回顾
toc: true
mathjax: true
categories:

  - web前端基础
tags:
  - css
  - js
  - html
date: 2020-11-10 21:10:21
summary:
cover:
coverImg:
top:
img:
---

# webstorm工具的使用 

**谷歌和火狐的速度快,指的是解析页面js和css的速度**

**支持更多的新功能,如最新的html5 css3的新功能**

# HTML介绍

## HTML基本格式

```html
<!-- 
文档类型声明
作用:告诉浏览器按照当前标准解析代码 
注意它不是html标签
HTML5标准:不区分大小写,双标记的结束标记可以省略  一般不省略
HTML4.01 版本: 严格 过渡 框架集
XHTML: 严格的HTML,区分大小写,结束标记必须写上
DTD: 文档类型定义 等同于 DOCTYPE
-->
<!DOCTYPE html>
<html>
    <head lang="en">
        <!-- 字符集  -->
        <meta charset="UTF-8">
        <title>标题</title>
    </head>
    <body>
    
    </body>
</html>    
```

## 文本格式化标签

```html
<b>加粗 bold</b>
<i>斜体 italic</i>
<u>下划线 underline</u>
<del>删除线</del>
<s>删除线</s>
<em>强调 倾斜显示</em>
<strong>强调  加粗显示</strong>
<sup>上标</sup>
<sub>下标</sub>
<big>大号字体</big>
<small>小号字体</small>

<p>
	块级元素块级元素
</p>

```

## 列表

### 无序列表

```html
<!-- 无序列表
	ul: unorder list
	li: list item
ul和li的属性
type: 设置项目符号的类型 (css中为list-style-type)
取值:
disc: 黑色实心圆
circle: 黑色空心圆
square: 黑色实心正方形
none: 取消项目符号

-->
<ul>
    <li><a href="#" target="_blank">新窗口打开链接: 所有内容写在li里</a></li>
    <li></li>
    <li></li>
</ul>
```
### 有序列表
```html
<!--  有序列表
	ol: order list
	li: list item
ol和li的属性
type: 设置项目符号
取值: 
1: 数字
i: 小写罗马字母
I: 大写罗马字母
a: 小写字母
A: 大写字母

start: 从第几个开始 默认是从第一个开始 取值: number

reversed: 倒叙排列符号  取值: reversed 当属性和属性值相同 可以简写为属性
-->
<ol>
	<li><a href="#" target="_blank">新窗口打开链接: 所有内容写在li里</a></li>
    <li></li>
    <li></li>
</ol>
```

### 自定义列表

```html
<!-- 自定义列表
-->
<dl>
	<dt>标题</dt>
    <dd>描述</dd>
    <dd>描述</dd>
    <dt>标题</dt>
    <dd>描述</dd>
    <dd>描述</dd>
</dl>
```

## 表格

```html
<!--
	cellspacing: 单元格之间的距离
	cellpadding: 内容距离边框的距离
	colspan: 水平合并
	rowspan: 垂直合并
-->
<table border="1" width="600" height="600" algin="center" cellspacing="0">
    <caption>表格标题</caption>
    <tr>
    	<td colspan="2"></td>
        <td rowspan="2"></td>
    </tr>
    <tr>
    	<td rowspan="2"></td>
        <td></td>
    </tr>
    <tr>
        <td colspan="2"></td>
    </tr>
</table>
```

## form表单

```html
<!-- 
1. 表单的作用
提交数据,使页面具有交互性
form之间不能相互嵌套,一个页面可以有多个表单
默认为get提交

2. 标签
<form action="提交的地址" name="表单名称" method="提交的方式 get|post">
	内容
</form>

3. 表单元素的属性
type 类型
name 名称
value 当前值
checked 默认被选中,配合单选按钮和多选按钮来使用
selected 默认显示,配合option使用
readonly 只读
disable 禁用

get与post的区别:
1) get提交数据不安全,会在地址栏中显示,post安全
2) get提交数据大小有限制(不能大于2kb),post理论上没有限制
-->

<form action="#" name="form1" method="GET">
	姓名: <input type="text" name="userName" /><br/>
    密码: <input type="password" name="passwod" /><br/>
    性别: <input type="radio" name="sex" id="man"/><label for="man">男</label>
    	 <input type="radio" name="sex" id="woman"/><label for="woman">女</label><br/>
    爱好: <input type="checkbox" name="fav" id="sing"/><label for="sing">唱</label>
    	 <input type="checkbox" name="fav" id="jump"/><label for="jump">跳</label>
    	 <input type="checkbox" name="fav" id="rap"/><label for="rap">rap</label>
    	 <input type="checkbox" name="fav" id="basketball"/><label for="basketball">篮球</label><br/>
    <input type="submit" value="登录"/>
    <input type="reset" value="重置"/>
    <input type="button" value="没有任何功能"/>
    
    <button>提交</button>
    <button type="reset">重置</button>
    <button type="button">没有任何功能</button>
</form>
<!--
将编码格式改为二进制
enctype="multipart/form-data" 
作用: 将上传的文件转换为二进制
-->
<form action="#" name="form2" enctype="multipart/form-data">
    <p>
    	文件:<input type="file"/>
    </p>
    <p>
        隐藏域:<input type="hidden"/>
    </p>
    <p>
        照片提交按钮:<input type="image" src="图片路径"/>
    </p>
    <p>
        下拉列表:
        <select name="city">
            <option value="bj">北京</option>
            <option value="sh">上海</option>
        </select>
        <!-- optgroup 为选项分组 -->
        <select>
            <optgroup label="北京">
            	<option value="">大兴</option>
                <option value="">通州</option>
                <option value="">朝阳</option>
            </optgroup>
            <optgroup label="河北">
            	<option value="">石家庄</option>
                <option value="">张家口</option>
                <option value="">保定</option>
            </optgroup>
        </select>
    </p>
    <p>
        多行文本框:
        <textarea name="liuyan"cols="30" rows="10"></textarea>
    </p>
    <input type="submit"/>
</form>
```

## H5新增type属性

```html
<!--     
H5新增表单元素属性
autofocus 自动聚焦 一般写在第一个表单元素上
required 必填表单
placeholder 输入框提示内容 默认提示
multiple 输入多个 用逗号隔开 多配合邮箱和网址使用
min和max 最小值和最大值 配合数字和范围使用
minlength和maxlength 最小长度和最大长度
 
-->
<form action="" name="form3">
    <p>
        邮箱: <input type="email" minlength="2" maxlength="10" multiple autofocus required placeholder="请输入邮箱" />
    </p>
    <p>
        网址: <input type="url" />
    </p>
    <p>
        搜索: <input type="search" />
    </p>
    <p>
        数字: <input type="number" min="0" max="100" step="10"/>
    </p>
    <p>
        范围(滑块): <input type="range" min="0" max="100" step="10" value="20" />
    </p>
    <p>
        颜色:<input type="color" />
    </p>
    <p>
        电话: <input type="tel" />
    </p>
    <p>
        日期: <input type="date" />
    </p>
    <p>
        周: <input type="week" />
    </p>
    <p>
        月: <input type="month" />
    </p>
    <p>
        时间: <input type="time" />
    </p>
</form>
```

## 语义化标签

### 定义

看到标签知道表示的意思

正确的标签干正确的事情,例如网页标题用H标签,段落用P标签

### 优点

- 有利于搜索引擎收录
- 有利于屏幕阅读者去读取
- 有利于开发者维护

```html
<!--
div: 没有语义的块级容器
span: 没有语义的行内容器
-->
```

## H5新增语义化布局标签

```html
<!-- 
H5新增语义化布局标签不支持IE6 7 8
-->
<header>头部</header>
<nav>导航栏</nav>
<div>
    <article>
        文章
        <section>章节</section>
    </article>
    <aside>侧边栏</aside>
</div>
<footer>页脚</footer>
```

## H5新增视频和音频标签

```html
<!--
1. 视频(行内元素)
1) 支持格式 mp4 ogg(移动端) weM(高清格式)
2) 标签
<video>您的浏览器不支持视频</video>
3) 属性
src 必须属性 视频路径
autoplay 自动播放
loop 循环播放
controls 显示控制面板 各个浏览器可能有差异
muted 静音
width 宽度
height 高度
poster 视频播放前显示一张图片
preload 一边播放 一边缓存 如果是autoplay 可以忽略该属性

2. 音频(行内元素)
1) 支持格式 mp3 ogg wav
2) 标签
<audio>您的浏览器不支持音频</audio>
3) 属性
src 必须属性 视频路径
autoplay 自动播放
loop 循环播放
controls 显示控制面板 各个浏览器可能有差异
muted 静音
preload 一边播放 一边缓存 如果是autoplay 可以忽略该属性

3. 资源
1) 作用
给浏览器提供多种视频或音频格式的选择
2) 标签
<source/>
3) 属性
src 必须属性 路径
4) 例子
<video>
	<source src="video1.mp4"/>
	<source src="video1.ogg"/>
	<source src="video1.webM"/>
	您的浏览器不支持视频
</video>

-->

<video src="视频文件路径" width="300" controls loop muted poster="照片路径">
    您的浏览器不支持视频
</video>

<audio src="音频文件路径" autoplay loop muted>
您的浏览器不支持音频
</audio>
```

## H5新增标签

```html
<!-- 一般用于组合图片和文字使用(块级元素) 
	img标签本身是行内元素
-->
<figure>
	<img src="图片路径" alt="" />
    <figcaption>图片描述文字</figcaption>
</figure>

<!-- 细节(块级元素)
	标题左侧有交互小箭头 点击可以显示和隐藏内容
-->
<details>
	<summary>标题</summary>
    <p>
        内容.........
    </p>
</details>

<!-- 突出显示(行内元素)
	mark标签内的内容会加上黄色的背景颜色
-->
<p>
    内容内容内容<mark>内容内容</mark>内容内容内容内容内容内容内容
</p>

<!-- 刻度(行内元素)
属性
min和max 设置刻度的最小值和最大值
value 设置当前刻度值
low和high 设置最低预警值和最高预警值 当前刻度值低于最低预警值和高于最高预警值刻度会变色
-->
<meter min="0" max="100" value="60" low="20" high="80">您的浏览器不支持刻度</meter>

<!-- 进度条(行内元素) -->
<progress max="100" value="">您的浏览器不支持进度条</progress>

<!-- 数据列表(行内元素)
使用数据列表必须与input标签关联才能使用
-->
<input type="text" list="city" />
<datalist id="city">
	<option value="BJ">北京</option>
    <option value="SH">上海</option>
    <option value="GG">广州</option>
</datalist>

<!-- 画布(行内元素) -->
<canvas width="800">您的浏览器不支持画布</canvas>
```

## 实体字符

```html
<!--
HTML中存在不能识别的文本,可以用实体字符来代替
eg:
空格 HTML中只能识别一个空格 &nbsp;
< 小于 &lt;
> 大于 &gt;
...

-->
```

# CSS介绍

```html
<!--
1. css介绍
Cascading Style Sheets
层叠样式表 级联样式表 简称样式表

2. css文件后缀
.css

3. 作用
1)实现了内容与表现的分离
2)提高了代码的可重用性和可维护性

4. css特点
1) 继承性
子元素可以继承父元素的样式
2) 层叠性
一个元素可以设置多个样式
3) 优先级
优先级大的样式生效
优先级相同,后写的样式生效

5. css语法
css属性 属性:属性值; (html属性的语法: 属性="属性值")

6. css注释
/* 注释的内容 */
注释之间不能相互嵌套

-->
```

## css引入方式

```html
<!--
引入css的目的: 把html和css关联起来
1) 行内样式 内联样式   --只对当前元素生效
通过html的style属性

2) 内部样式    --只对当前页面生效

3) 外部样式   --实现了内容与表现的完全分离,提高了代码的可重用性和可维护性
① 新建.css文件
② 在head标签中通过link标签引入css
一个html可以引入多个css文件
同一个css文件可以被多个html引用

4) 导入式 
在style标签中通过 
① @import "css文件路径" 
② @import url("css文件路径")
来导入css样式

优先级:
行内样式>内部样式=外部样式

@import与link的区别:
1) 加载顺序不同,@import先加载html文件再加载css文件,link同时加载html和css文件
2) @import只能引入css文件,link还可以引入其它内容
<link ref="icon" href="图标文件路径" />
3) @import有兼容性(IE5以上支持) link没有兼容性
4) JavaScript操作DOM时,只能操作link引入的css
5) @import会增加页面的http请求

-->
1) eg:
<div style="width: 300px;height: 400px;background-color: red;"></div>

2) eg:
<head>
	<style>
        element {
            width: 100px;
            height: 200px;
            backgroud-color: green;
        }
    </style>
</head>

3) eg:
<head>
	<link rel="stylesheet" href="css文件路径" />
</head>

4) eg:
<style>
	@import "css文件路径";
    @import url("css文件路径");
</style>
```

## css选择器

```html
<!--
1. 基础选择器
1) 全局选择器 通用选择器
*{}
范围: 选中页面所有元素

2) 元素选择器
div{}
p{}
a{}
img{}
b{}
范围: 选中所有指定的元素

3) 类选择器
.className{}
范围: 所有由class属性且属性值等于className的元素
类名可以重复
一个class可以起多个名字,用空格隔开
命名规则:
① 可以包含数字 字母 -
② 不能以数字开头
③ 起有意义的名字

4)ID选择器
#idName{}
ID具有唯一性

选择器优先级: 选中范围越小 优先级越高 
	行内样式>ID选择器>类选择器>元素选择器>全局选择器
权重  1000     100      10       1
混合使用时,可权重相加判断优先级

5) 合并选择器
选择器1,选择器2,选择器3,...{
	共同样式
}
-->
```

## 字体属性

```css
/*
字体属性具有继承性
颜色的取值:
1) 关键字 red green yellow
2) 16进制 (0-9 a-f) 黑色: #000000 简写 #000  白色: #ffffff 简写 #fff
3) rgb(0,0,0) 取值 0-255 参数颜色顺序 红 绿 蓝
4) rgba(0,0,0,.5) a:透明度,取值0-1 0:完全透明 1:不透明 0.5可简写成.5

1. 字体颜色
color: red;

2. 字体大小
font-size: 16px;
浏览器支持的最小字体为12px

3. 字体是否加粗
font-weight: normal/bold/100-900;
400=normal 700=bold

4. 字体是否倾斜
font-style: normal/italic;

5. 字体 (默认宋体)
font-family: 字体1,字体2,字体3;
首先使用字体1,若浏览器不支持字体1,则使用字体2,依次使用,若都不支持则使用默认字体
注意: 一个字体有多个单词 需要加引号

*/
```

## 文本属性

```css
/*
文本属性具有继承性
1. 元素内容的水平对齐方式
text-align: left/center/right;

2. 文字装饰
text-decoration: underline(下划线)/none/line-through(删除线)/overline(上划线);

3. 英文字母大小写转换
text-transform: uppercase(大写)/lowercase(小写)/capitalize(每个首字母大写);

4. 首行缩进
text-indent: ;
取值 px em
px: 绝对单位 像素
em: 相对单位 相对于当前字体大小  默认为16px 1em=16px
rem: 相对单位

*/
```

## 列表属性

```css
/*
列表属性具有继承性
1. 设置项目符号
list-style-type: none;

2. 设置项目符号为图片(一般不用)
list-style-image: url("图片路径");

3. 设置项目符号的位置
list-style-position: outside/inside;

4. 简写
list-style: none;

*/
```

## 行高

```css
/*
行高具有继承性
line-height: ;
设置的是一行文字的高度
当行高等于高,一行文字垂直居中
可以设置为px/number(设置为number时,注意此时的行高等于当前文字的像素 × number  一般不用number)

*/
```

## 背景属性

```css
/*
1. 背景颜色
background-color: transparent;(默认为透明)
颜色的取值:
1) 十六进制 #000  #fff
2) 关键字 red green yellow
3) rgb(0,0,0)  rgb(255,255,255)
4) rgba(0,0,0,.5)  a: 透明度,取值为0-1

2. 背景图片
background-image: url("图片路径");
默认水平垂直平铺
注意: img元素与背景图片的区别
img元素: 父元素放不下 会溢出
背景图片: 父元素多大  显示多大

3. 背景图片是否平铺
bakcground-repeat: repeat/no-repeat/repeat-x/repeat-y;

4. 背景图片大小
background-size: x y;
取值 px % cover contain
cover: 覆盖整个背景区域,背景图片可能显示不完全
contain: 背景图片拉伸至足够大,但是背景区域可能覆盖不完全

5. 背景图片定位
background-position: x y;
默认在左上角 0 0
取值 px % left right center top bottom
当只取一个值 第二个值默认居中
取正值,背景图片向右下走 取负值,背景图片向左上走

6. 背景图片固定
background-attachment: scroll/fixed;

7. 简写
background: 颜色 图片 平铺 大小 定位 固定;
当简写属性和单个属性同时存在时,单个属性要写在简写属性后面

*/
```

## 关系选择器

```css
/*
1. 后代选择器
选择器1 选择器2{}
选中所有后代

2. 子代选择器
选择器1>选择器2{}
选中所有直接子代

3. 相邻兄弟选择器
选择器1+选择器2{}
平级 挨着 后面的一个兄弟

4. 通用兄弟选择器
选择器1~选择器2{}
平级 后面的所有兄弟

*/
```

## 内容溢出

```css
/*
1. 元素内容溢出
overflow: hidden/auto/scroll;
hidden: 溢出部分隐藏
auto: 自动 有溢出,显示滚动条,没有溢出则不显示滚动条
scroll: 溢不溢出都显示滚动条

2. 一行文字溢出省略号显示
文字在同一行显示
white-sapce: nowrap;
溢出部分隐藏
overflow: hidden;
文字溢出省略号显示
text-overflow: ellipsis;

*/
```

## 表格属性

```css
/*
1. 表格宽高
width: ;
height: ;

2. 背景颜色
background-color: ;

3. 背景图片
background-image: url("");

4. 表格内容水平对齐方式
text-align: left/center/right;

5. 单元格内容垂直对齐方式
vertical-align: top/middle/bottom;

6. 边框折叠  相当于cellspacing="0"
border-collapse: collapse;

*/
```

## css其他补充属性

```css
/*
1. 字符之间的距离
letter-spacing: ;

2. vertical-align: ;
1) 在td中
td内容的垂直对齐方式
2) 离开td
容器中元素和内容的垂直对齐方式

转换成td
display: table-cell;

*/
```

## 标准盒模型

```css
/*
1. 盒模型
HTML每一个元素都可以看做一个盒模型

2. 标准盒模型(W3c盒模型) ---浏览器默认
1) 组成部分
content(内容)+padding(内边距)+border(边框)+margin(外边距)

2) 实际宽度
width+padding(左右)+border(左右)+margin(左右)

3) content 内容区域
width: ; 取值 px %(相对于父元素)
height: ; 取值 px %(相对于父元素)
min-width: ; 最小宽度
max-width: ; 最大宽度
min-height: ; 最小高度
max-height: ; 最大高度
块级元素默认宽度为100%,行内元素默认宽度由内容撑开
高度默认由内容撑开
块级元素可以设置宽高,行内元素设置宽高不生效(图片归为行内元素 实际是行内块元素 可以设置宽高)

4) border 边框
border-style: solid(实线)/dashed(虚线)/dotted(点线)/double(双实线)/none; 必须属性,默认为黑色 3px
border-color: ;
border-width: ;
简写: border: 3px solid green;
单边属性:
border-top: ; border-top-style: ; border-top-color: ; border-top-width: ;
border-bottom: ;
border-left: ;
border-right: ;
单边属性也可以简写
border-top: 5px solid yellow;
应用:
画三角形
原理: 取消div的宽高,设置其他三边框的边框颜色为transparent,再设置边框长度即可(IE6不支持transparent,可以将原先需要透明的边的边框设置边框样式为dashed)
.div1{
	width: 0;
    height: 0;
    border-style: solid;
    border-color: red transparent transparent transparent;
    border-width: 50px 50px 50px 50px;
}

5) padding 内边距 不能取负值和auto
设置内容距边框的距离
语法: 
padding: value; 四周
padding: value value; 上下 左右
padding: value value value; 上 左右 下
padding: value value value value; 上 右 下 左
单边属性: 
padding-top: ; 上内边距
padding-bottom: ; 下内边距
padding-left: ; 左内边距
padding-right: ; 右内边距
注意: padding会撑大容器

6) margin 外边框 可以取正负和auto
设置元素之间的距离 
外边距是透明的
语法: 
margin: value; 四周
margin: value value; 上下 左右
margin: value value value; 上 左右 下
margin: value value value value; 上 右 下 左
单边属性: 
margin-top: ; 上外边距
margin-bottom: ; 下外边距
margin-left: ; 左外边距
margin-right: ; 右外边距

*/
```

### 块级元素水平居中

```css
.div1{
	width: 200px;
	height: 200px;
	margin: 0 auto;/*核心代码*/
}
```

### 垂直方向上外边距合并问题

**当垂直方向上外边距相撞时,取较大值**

### margin-top问题

**问题:**

当第一个块级子元素设置margin-top时,父元素跟着一起下来

**解决方案:**

1) 父元素加overflow: hidden; (找到原位置)

2) 父元素或子元素浮动(不提倡使用,除非父元素或子元素在布局时恰好使用到浮动)

3) 父元素加border-top: 1px solid transparent; (改变盒模型 不提倡使用)

4) 父元素加padding-top: 1px; (改变盒模型 不提倡使用)

##  伪类选择器(包括CSS3新增)

```css
/*
:链接 表示一种状态
:link 点击之前(只适用于a)
:visited 点击之后(只适用于a)
:hover 鼠标悬停(适用于所有元素)
:active 鼠标按下(适用于所有元素)
顺序: link visited hover active

css3新增伪类选择器:
:first-child  第一个子元素是...
:last-child  最后一个子元素是...
:nth-child(number/even/odd/倍数)  第几个子元素是...
even: 偶数
odd: 奇数
倍数: 2n  3n
:only-child 唯一一个子元素是...
:empty 空的子元素(元素之间任何内容都没有)
:not() 否定 (即不选中该元素)
:focus 获取焦点时的样式
:checked 默认被选中时的样式(配合单选按钮和多选按钮)

eg: 若div1中的第一个子元素不是div 则color不生效(即没有选中该元素)
.div1>div:first-child{
	color: red;
}

*/
```

## 伪对象选择器

```css
/*
语法:
:before{}或者::before{}
:after{}或者::after{}

1) 添加文字
2) 添加图片
3) 添加块级元素

*/
<div class="box">盒子</div>
1) eg: 
.box:before{
    content: "前面"
}
.box:after{
    content: "后面"
}

2) eg:
.box:befre{
    content: url("图片路径");
}
.box:after{
    content: url("图片路径");
}

3) eg:
.box:before{
    content: "";
    /*转换为块级元素*/
    display: block;
    width: 200px;
    height: 200px;
    background-color: red;
}
.box:after{
    content: "";
    display: block;
    width: 200px;
    height: 200px;
    background-color: red;
}

```

## 属性选择器

```css
/*
利用的是HTML的属性
[属性]
[属性=属性值]
元素[属性=属性值]
元素[属性^=属性值] 开头(属性值)
元素[属性$=属性值] 结尾(属性值)
元素[属性*=属性值] 包含(属性值)

*/
eg:
[class="box"]{}
div[class="box"]{}
div[class^="t"]{}  /*选中类名开头为t的div元素*/
```

## 元素透明度 opacity 

```css
/*
opacity:
设置整个元素的透明度
取值 0-1 (eg: opacity: .55;)
0: 完全透明
1: 不透明

*/
```

## 怪异盒模型

```css
/*
怪异盒模型 IE盒模型
1. 组成部分
content+border+margin+padding

2. 实际宽度
width+margin (width包含了padding和border)

3. 盒模型相互转换
box-sizing: content-box; 默认值 标准盒模型
box-sizing: border-box; 怪异盒模型

*/
```

## 浮动

```css
/*
1. 原理
浮动后脱离文档流(排除到普通流之外)
浮动后在页面不占据位置(原位置不保留)
浮动碰到父元素的边框或浮动元素的边框就会停止
浮动不会重叠
浮动只有左右浮动
浮动后所有元素转换为块级元素

2. 语法
float: left/right/none;

3. 清除浮动的影响
子元素浮动,父元素高度坍塌,对后面的元素产生影响
1) 受影响的元素加clear: left/right/both; --浮动元素的父元素的高度依旧坍塌
2) 给浮动元素的父元素加高 -- 适用于高度方便计算
3) 浮动元素的父元素加overflow: hidden;(自动找到高度)
4) 空div法
浮动元素后面加一个空div
空div{clear: both;}
5) 伪对象法 (常用)
浮动元素的父元素::after{
	content: "";
	display: block;
	clear: both;
}
*/
```

## display属性

```css
/*
1. 定义
每一个元素都自带display属性

2. 属性
display: ;

3. 属性值
block 块级元素
inline 行内元素
inline-block 行内块,即在同一行显示,也可以设置宽高 注意:行内块会识别代码之间的空白 (一般不用)
常见的行内块元素: img video audio input button
none 隐藏,隐藏后不占据位置
flex 弹性盒模型
table 表格
table-cell 单元格 td

4. display: none; visibility: hidden; opacity: 0; overflow: hidden;的区别
display: none; 隐藏自己 隐藏后不占据位置
visibility: hidden; 隐藏自己 隐藏后原位置保留
opacity: 0; 透明度为0 隐藏自己 隐藏后原位置保留
overflow: hidden; 溢出部分隐藏
*/
```

## 元素定位 position

```css
/*
1. 属性
position: ;

2. 属性值
1) static 静态定位 默认值

2) relative 相对定位 
相对于自己原位置定位
定位后原位置保留
配合left right top bottom移动

应用场景:
① 自己小范围移动
② 配合绝对定位使用

3) absolute 绝对定位 定位后原位置不保留
绝对定位相对于已经定位的父元素定位(相对定位 绝对定位 固定定位)  父元素一般用相对定位 
如果父元素没有定位 逐级向上找 最后相对于body定位
配合left right top bottom移动

应用场景:
① 形成独立的一层
推荐: 给绝对定位的父元素加相对定位

4) fixed 固定定位
相对于浏览器窗口定位
定位后原位置不保留
配合left right top bottom移动

应用场景:
① 固定在页面某个位置

*/
```

## 在页面中不占据位置的属性设置

```css
float: left;
float: right;
display: none;
position: fixed;
position: absolate;
```

## 堆叠顺序 z-index

```css
/*
z-index: number;
取值越大,层级越往上
可以取负值 不推荐
必须配合定位使用(相对定位 绝对定位 固定定位)

*/
```

## 居中问题

### 元素内容水平居中

```css
text-align: center;
```

### 块级元素水平居中

```css
margin: 0 auto;
```

### 一行文字垂直居中

```css
/*
设置行高等于高
*/
eg:
width: 200px;
height: 50px;
line-height: 50px;
```



### 多行内容垂直居中

```css
margin: 20px 0; // 加在自己上
padding: 20px 0;// 加在父元素上
```

### 子元素在父元素中水平垂直居中  (六种方法)

```html
<style>
    .box {
        width: 500px;
        height: 500px;
        background-color: red;
    }
    .box1 {
        width: 200px;
        height: 200px;
        background-color: green;
    }
</style>

<div class="box">
	<div class="box1"></div>
</div>
```

```css
answer 1): 使用margin
.box {
	overflow: hidden; // 找到父元素的位置
}
.box1 {
	margin: 150px auto;
}
```

```css
answer 2): 使用定位 需要计算
.box {
    position: relative;
}
.box1 {
    position: absolute;
    top: 150px;
    left: 150px;
}
```

```css
answer 3): 使用padding
.box {
    padding: 150px;
    box-sizing: border-box;
}
```

```css
answer 4): 使用table-cell
.box {
    display: table-cell;
    vertical-align: middle;
}
.box1 {
    margin: 0 auto;
}
```

```css
answer 5): 使用定位 不用计算
.box {
    position: relative;
}
.box1 {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%); //若已知子元素的宽高 可以使用margin设置
}
```

```css
answer 6): 使用弹性盒法
```

## 圆角 border-radius

```css
/*
1. 圆角	
border-radius: ;
取值: px %
取值个数: 1-4
取一个值: 四个角
取两个值: 左上角、右下角  右上角、左下角
取三个值： 左上角  右上角、左下角  右下角
取四个值： 左上角开始顺时针旋转

画圆 border-radius: 50%;

*/
```

## 阴影 box-shadow/text-shadow

```css
/*
1. 盒阴影 box-shadow
box-shadow: 水平方向的位置 垂直方向的位置 模糊度 尺寸(扩展度) 颜色 位置;
水平方向的位置: 必须属性 取值为正负
垂直方向的位置: 必须属性 取值为正负
模糊度: 可选属性 取值为正值
尺寸: 可选属性 取值为正负
颜色: 可选属性 取值 16进制 关键字 rgb rgba
位置: 可选属性 取值 outset(默认)/inset

*/

eg:
1) 三个方向
box-shadow: 0 10px 30px gold;
2) 四个方向
box-shadow: 0 0 30px gold inset;

/*
2. 字阴影 text-shadow
text-shadow: 水平方向的位置 垂直方向的位置 模糊度 颜色;
水平方向的位置: 必须属性 取值为正负
垂直方向的位置: 必须属性 取值为正负
模糊度: 可选属性 取值为正值
颜色: 可选属性 取值 16进制 关键字 rgb rgba

*/
```

## 浏览器厂商前缀 (解决浏览器对css3新特性的支持)

```css
/*
解决浏览器对css3新特性的支持
css3新特性: 圆角 盒阴影 字阴影 伪对象选择器 属性选择器 兄弟选择器等...

浏览器				内核				厂商前缀
谷歌				blink内核			-webkit-
苹果				webkit内核		-webkit-
火狐				gecko内核			-moz-
IE				 trident内核		  -ms-
欧朋 				blink内核			-o-

*/
```

## css hack (解决IE6 7 8 的兼容性问题)

```css
/*
解决IE6 7 8 的兼容性问题
1) 条件注释法 可以在body中 head中使用 不能直接在style中使用
<!--[if 条件]>
<![endif]-->

2) 属性前缀和后缀
前缀 + - _ * #
后缀 \0 \9 \9\0 !important(属性优先级最高)

*/

eg: 
<!--[if IE 7]>
<style>
body {
    text-align: left;
}
</style>
<![endif]-->
```

## 背景渐变 (线性/径向)

```css
/*
1. 线性渐变
background: linear-gradient(方向, 颜色1, 颜色2, ...);
方向默认从上到下  to bottom
eg: to right 、 to right bottom
    deg: 弧度
background: linear-gradient(120deg, #ff910e,#ffd037);

2. 径向渐变 / 射线渐变  /  扇形渐变
background: -webkit-radial-gradient(渐变的中心位置, 渐变的形状, 颜色1, 颜色2, ...);
默认的渐变中心点在宽高的一半
默认的渐变形状为椭圆
eg:
background: -webkit-radial-gradient(top left, circle, red, yellow, green);

*/
```

## 弹性盒模型

```css
/*
弹性盒模型 伸缩盒模型 flex box
在弹性盒中float和clear不生效
1. 作用 
适应不同的屏幕大小
多用于移动端布局

2. 父元素上的属性
1) 开启弹性盒模型
display: flex;
开启弹性盒模型后,子元素默认水平排列

2) 弹性盒的方向
flex-direction: row/column/row-reverse/column-reverse;
row: 默认值 子元素水平排列
column: 子元素垂直排列
row-reverse: 子元素在水平方向上倒序排列
column-reverse: 子元素在垂直方向上倒序排列

3) 设置子元素在主轴的对齐方式
默认X为主轴,Y轴为侧轴
当flex-direction: column;时,Y轴为主轴,X轴为侧轴
justify-content: flex-start/flex-end/center/space-around/space-between;
flex-start: 默认值 弹性盒的主轴开始
flex-end: 弹性盒的主轴结束
center: 主轴居中
space-around: 两侧(上下)是中间距离的一半 (分配的是父元素中的剩余空间)
space-between: 在子元素之间平均分配父元素剩下的空间,左右(上下)两端没有空间

4) 设置子元素在侧轴的对齐方式
align-items: flex-start/flex-end/center;
flex-start: 默认值 弹性盒的侧轴开始
flex-end: 弹性盒的侧轴结束
center: 侧轴居中

3. 子元素上的属性
设置弹性盒之间的宽度 (会跟随页面的缩放而改变 随着比例改变)
flex-grow: number;

*/
```

## 转换 transform

```css
/*
1. 作用
使元素在位置或形状上发生一定的改变
比如: 位移 旋转 缩放 倾斜

2. 属性
transform: translate() rotate() scale() skew();

3. 属性值
1) 位移 单位 px %
transform: translate(x, y)/translateX()/translateY();  x y 可以取正负

2) 旋转 单位 deg (弧度) 取正值,顺时针旋转 取负值,逆时针旋转   
transform: rotate(30deg)/rotateX()/rotateY();
改变旋转的中心点: transform-origin: right bottom; 默认中心点为宽高的一半

注意: 旋转会改变整个坐标轴,当位移和旋转同时存在时,建议位移写在旋转的前面

3) 缩放 取值为number 可以取正负
transform: scale()/scaleX()/scaleY();
取值在0-1 缩小
取值大于1 放大
默认值为1

4) 倾斜 单位 deg (弧度)
transform: skew(xdeg, ydeg)/skewX()/skewY();

*/
```

## 过渡 transition

```css
/*
1. 作用 
使元素从一个样式平滑的过渡到另一个样式

2. 过渡必须有触发事件
例如鼠标悬停 鼠标点击等...

3. 过渡的属性
1) 过渡的属性 必选 可以取多个属性(eg: width color) 也可以直接 all
transition-property: ;
可以过渡的属性:
① 取值为颜色
② 取值为数值
③ 转换 transform: ;
④ 阴影 box-shadow: ; text-shadow: ;
⑤ 背景渐变 linear-gradient: ; ... 

2) 过渡的持续时间  必选 单位 s/ms 可以取正值
transition-duration: 1s;

3) 过渡的速度变化类型
transition-timing-function: ;
取值:
ease  先加速后减速
ease-in  加速
ease-out  减速
ease-in-out  先加速后减速
linear  匀速

4) 延迟时间 单位 s/ms 延迟多久开始触发动作 
transition-delay: ;
可以取负值,表示把这段时间的效果直接跳过

5) 简写
transition: all 持续时间 速度变化类型 延迟时间;

*/
```

## 动画

```css
/*
1. 动画和过渡的区别
1) 过渡只能制作简单的动画,动画可以制作复杂的动画
从一个样式到另外一个样式,动画可以控制过程
2) 过渡必须有触发事件,动画可以没有

2. 定义动画
@keyframes donghua {
	0%或者from{
	//css样式
	}
	百分比{
	//css样式
	}
    100%或者to{
	//css样式
    }
}
浏览器兼容:
@-webkit-keyframes name{...}

3. 调用动画(关键帧动画)
-webkit-animation: ;
animation: name(必须) 持续时间(必须 正值) 速度变化类型(同过渡) 延迟时间(可正负) 播放次数(number/infinite) 播放方向(alternate: 偶数次倒序播放) 动画停在最后一帧(forwards);


4. 属性
animation-name: ; 动画的名称
animation-duration: ; 持续时间
animation-timing-function: ; 速度变化类型
animation-delay: ; 延迟时间
animation-iteration-count: ;播放次数
animation-direction: ; 播放方向
animation-fill-mode: ; 动画停在最后一帧

animation-play-state: paused; 动画暂停播放 不简写

*/
```

## 媒体查询

```css
/*
PC端布局 --float
移动端布局 --dispaly: flex;
响应式布局 --媒体查询 media query

1. 响应式布局的定义
写一次样式适用所有终端(PC端 iPad 移动端)

2. 语法
PC端
@media screen and (min-width: 992px) {
	//PC端的样式
}
iPad端
@media screen and (max-width: 991px) and (min-width: 768px) {
	//iPad端的样式
}
移动端
@media screen and (max-width: 767px) {
	//移动端的样式
}

*/
```

## css雪碧图

```css
/*
1. css sprite  css精灵 雪碧图
1) 定义
雪碧图是一项图片整合技术
把许多小图整合到一张大图上

2) 优点
① 减少图片的字节数
② 减少页面的http请求
③ 减少命名困扰

3) 原理
① 定义一个容器 设置宽高
②  background-image: url(""); 引入图片
③ background-position: ;移动背景图片
默认背景图片显示左上角, 0 0位置
注意: 容器是不可以移动的,移动的是背景图片

*/
```

## 多列

```css
/*
1. 作用
将容器中的文本分为多列

2. 属性
column-count: 3; //将容器中的文本分为三列
column-gap: 30px; // 每列间隔30px
column-rule: 2px solid red; // 每列之间的间隔线 线的长度与内容有关

*/
```

# JavaScript介绍

## JavaScript的组成本分

ECMAScript  核心JS  包含了js的基础语法、变量、数据类型、运算符、分支结构、循环结构、函数、数组、对象等

DOM  文档对象模型  规定了一套管理HTML文档的机制

BOM  浏览器对象模型

## JavaScript引入方式

### 内部引入

```html
<script>
	js语句
</script>
<!-- 
	script标签可以写在页面任何位置
	建议: 写在body结束标签之前
-->
```

### 外部引入

```html
<script src="js文件路径"></script>
<!--
	script标签可以写在页面任何位置
	建议: 写在head标签中	
-->
```

**注意: 外部方式和内部方式不能共用一个script标签,当共用一个script标签时,外部方式生效**

## JavaScript输出方式

```js
/*
1. 输出到控制台
console.log();

2. 输出到页面
document.write();
HTML标签可以直接在js中应用
eg: 
document.write('<h2>这是二号字体</h2>');

3. 弹出警示框
window.alert();
简写为alert();

注意: alert会阻止页面程序的执行

*/
```

## JavaScript注释

### 单行注释

```js
// console.log("hello world");
```

### 多行注释

```js
/*
	document.getElementById('div1');
	document.write('hello world');
*/
```

## JavaScript语法

```js
/*
1. 区分大小写 (大小写敏感)

2.js语句以换行或分号结尾

3. 推荐: 一行只写一条语句并且以分号结尾

4. js会忽略多余的空格

*/
```

## 变量

```js
/*
1. 变量的定义
值可以改变的量称为变量

2. 变量的作用
存储数据的容器

3. 变量的声明
var 变量名;

4. 变量的赋值
变量名 = 值;
等号右边的值赋值给左边

5. 变量的初始化
声明变量的同时,给变量赋值,称为变量的初始化
var num = 1;

6. 一条语句可以声明多个变量,用逗号隔开
var num1 = 2, num2 = 3, num3 = num1 + num2;
var num1,num2,num3;

7. 声明变量没有赋值,默认为undefined

8. 不声明变量直接调用,会报错 提示该变量未定义

9. 重新声明,js的值不会丢失
var x = 10
var x;
console.log(x); // 10

10. 重新赋值,后面的值会替换前面的值
var x = 10;
x = 100;
console.log(x); // 100

11. 变量的声明提升
js变量的声明会提前到所有代码的最上面,赋值留在原地
console.log(x); // undefined
var x = 10;

12. 不写var的情况
不写var声明的变量是全局变量,作用域不受控制

13. 变量的命名规则
1) 区分大小写
2) 可以包含数字 字母 数字 下划线 $
3) 不能以数字开头
4) 不能是js的关键字和保留字 eg: var
5) 见名知意 起有意义的名字
6) 多个单词用驼峰命名法
小驼峰命名法: userNameLast 推荐使用
大驼峰命名法: UserNameLast

*/
```

## 数据类型  typeof 用于判断变量的类型

### 1. number类型

```js
/*
number类型:
所有数字(不分正负 不分整浮 不分大小 不分进制)
infinity 无穷大  -infinity 无穷小
    10/infinity;//0
    2/0;//infinity
    infinity/infinity;//NaN
    infinity/2;//NaN
    infinity === infinity;//true
    Number.isFinite();//检查提供的值是否是有限数 返回布尔类型
NaN

*/
```

### 2. string类型

```js
/*
string类型:
引号包裹的任何文本
单双引号都可以
注意: 两个string类型数据比较大小,比较的是ASCII值

*/
```

### 3. 布尔类型

```js
/*
布尔类型只有两个值: true false

*/
```

### 4. undefined  未定义类型

```js
/*
未定义类型表示数据类型不确定
声明一个变量,没有赋值,默认值为undefined,数据类型也为undefined

*/
```

### 5. null  空类型

```js
/*
null表示的数据类型确定为object
null用来主动释放对象
注意: 
var x;
console.log(typeof x);// object

*/
```

### 6. object  对象类型(引用数据类型)

```js
/*
大括号包含的一组值
对象由键值对构成,多个键值对之间用逗号隔开,最后一个键值对后面不加逗号
键值对是由键名和键值组成,键值和键名之间用冒号隔开
eg:
var obj = {
	name: 'Tom',
	age: 11,
	sex: '男'
};

*/
```

## 运算符

### 比较运算符

```js
/*
比较两个值的大小,返回一个布尔值(true false)
>  <  >=  <=  !=  !==  ==  ===
==: 等于,只判断数值
===: 全等,绝对等于,即判断数据类型又判断数值
!=: 不等于,==取反
!==: 不全等,===取反

注意:
undefined == null;// true 都没有值
undefined === null;// false undefined的数据类型为undefined,null的数据类型为object
NaN == NaN;// false 
NaN === NaN;// false
NaN != NaN;// true
NaN !== NaN;// true

*/
```

### 逻辑运算符

```js
/*
连接多个表达式,返回一个布尔值(false true)
&&: 逻辑与 并且 所有的表达式都为true,结果才为true,只要有一个表达式为false,结果就是false
||: 逻辑或 或者 所有的表达式都为false,结果才为false,只要有一个表达式为true,结果就是true
!:  逻辑非 取反 表达式结果为false,取反就是true;表达式结果为true,取反就是false

注意: 逻辑与的优先级大于逻辑或

*/
```

### 赋值运算符

```js
/*
=: 等号右边的值赋值给等号左边 x=5;
+=: x+=y 相当于 x=x+y;
-=: x-=y 相当于 x=x-y;
*=: x*=y 相当于 x=x*y;
/=: x/=y 相当于 x=x/y;
%=: x%=y 相当于 x=x%y;

*/
```

### 算数运算符

```js
/*
注意运算符的优先级
+  - *  /  %(取余 模)  ++(自增)  --(自减)
%: 取余,做除法,要余数   应用: 判断奇偶数 倍数 
++: 自增,相当于给自己加1 x++ 相当于 x=x+1
--: 自减,相当于给自己减1 x-- 相当于 x=x-1
前后++ -- 都是对自己加或减1 
eg: 
var x=10;
console.log(x++);//10
console.log(++x);//11

加运算遇到字符串,直接进行字符串的拼接,返回string类型
- * / %遇到字符串,都转换成number类型进行计算,如果不能转换为数字,返回NaN,数据类型为number
true转换为1 false转换为0

*/
```

## 分支结构

### 单分支结构

```js
/*
if(条件){
	满足条件执行的语句
}

*/
```

### 双分支结构

```js
/*
if(条件){
	满足条件执行的语句
}else{
	不满足条件执行的语句
}

*/
```

### 多分支结构

```js
/*
if(条件){
	满足当前条件执行的语句
}else if(条件){
	满足当前条件执行的语句
}else if(条件){
	满足当前条件执行的语句
}else{
	以上条件都不满足,执行的语句
}

注意: 
1. 最后的else可以省略
2. 多选一执行,条件一旦满足,就不向下执行 (多分支结构条件判断为顺序执行)

*/
```

## 动态输入框

```js
/*
1. 语法
prompt("提示", 默认值);

2. 注意
1) 默认值可以省略
2) 返回string类型

*/
```

## 类型转换

```js
/*
string类型转换为number类型(强制转换)
parseInt(): 转换为整数,只取整数部分,不会四舍五入
parseFloat(): 转换为小数,只能识别一个小数点

string类型转换为number类型(隐式转换)
- * / %

*/
```

## 循环结构 break/continue

```js
/*
1. 语法
for(循环变量; 循环条件; 执行规律){
	循环语句
}

2. 执行过程
1) 判断循环变量是否满足循环条件,不满足直接跳出循环
2) 满足,进入循环,执行循环语句
3) 执行循环规律,判断循环变量是否满足循环条件,不满足直接跳出循环 ...

循环结构关键字
break: 退出整个循环
continue: 退出本次循环,继续下一轮循环

*/
```

## 字符串

```js
/*
1. 定义
引号包含的任意内容
引号:单双引号都可以

2. 字符串可以相互嵌套
单引号嵌套双引号
双引号嵌套单引号

3. 转义字符 \(反斜杠)
加在产生歧义内容的前面
eg: 
var str = 'Hello \'world\'';

4. 一个字符串需要写在同一行,换行显示会报错
解决:
1) 使用加号(+) 对字符串进行拼接
2) 使用转义字符(\)对字符串后的空格进行转义

5. 字符串的属性
1) 字符串的长度
string.length
注意: 汉字 数字 英文 标点符号等都算一个长度
eg:
var str = 'hello';
var len = str.length;// 5

6. 字符串的方法
1) charAt(index) 返回下标索引所对应的字符 最后一个下标 str.length-1
注意: index的索引从0开始

2) charCodeAt(index) 返回下标索引所对应的字符的Unicode编码
注意: index的索引从0开始
0: 48
a: 97
A: 65

3) concat(str1, str2, ...) 拼接字符串

4) 截取字符串
索引都是从0开始
不改变原字符串 
当只有一个参数,表示从开始位置截取到最后
截取时含头不含尾 包含开始位置,不包含结束位置
① str.subString(startIndex, endIndex);
当开始位置下标大于结束位置下标时,自动调换
② str.subStr(startIndex, length) length为截取长度
③ str.slice(sstartIndex, endIndex)
当开始位置下标大于结束位置下标时,返回空字符串

5) 查找字符串
如果查找不到,返回-1
下标索引都是从0开始
① str.indexOf(searchStr, index)
从前往后查找,返回第一个符合条件的下标
index: 表示开始查找的位置,默认从0开始
② str.lastIndexOf(searchStr, index)
从后往前查找,返回后面第一个符合条件的下标
index: 表示开始查找的位置,默认从最后一个开始

6) trim() 去掉字符串两端多余的空格
str.trim()

7) 英文字母大小写转换
转换为大写
str.toUpperCase()
转换为小写
str.toLowerCase()

8) 查找字符串 多配合正则使用
① str.search(searchStr) 返回具体索引
默认返回第一个符合条件的下标
如果查找不到,返回-1
② str.match(searchStr)
默认返回第一个符合条件的具体字符数组(数组中包含查找的字符 第一个符合条件的索引下标 原字符串)
如果查找不到,返回null

9) replace() 替换字符串
str.replace(旧字符串, 新字符串)
默认情况下替换符合条件的第一个
不改变原字符串

10) split() 分割字符串,返回数组
str.split(分隔符)


*/
```

## 数组

```js
/*
1. 定义
中括号包含的有序的数据集合
数组是按照一定顺序排列的一组值
按照下标的顺序排列,从0开始

2. 作用 
存储数据的容器

3. 数组里的数据称为数组元素
数组元素可以是任何数据类型

4. 数组的本质是对象
数组是对象的一种本质表现形式

5. 数组的创建
1) 字面量法
var arr = [];
var arr = [数组元素1, 数组元素2, ...];
2) new方法
var arr = new Array();
var arr = new Array(数组元素1, 数组元素2, ...);
区别:
当只有一条数据,且数据类型为number
字面量法表示下标为0,长度为1,数组元素为此数字
new方法表示长度为此数字,数组元素为empty 

6. 数组的空位
两个逗号之间没有值,称为数组的空位
最后一个数组元素后面加逗号不会产生空位,建议不写

7. 数组的长度
arr.length
数组的长度可以赋值 arr.length = 4;
赋值 > 原长度 多余的数组元素空位补全
赋值 < 原长度 多余的数组元素直接忽略

8. 数组的调用
arr[index]

9. 数组的赋值
arr[index] = 'XXX';

10. 数组的遍历
1) for循环
for(var i=0; i<arr.length; i++){
	console.log(arr[i]);
}
2) 快速遍历
for(var i in arr){
	console.log(arr[i]);
}

11. 判断是否为数组
Array.isArray(arr)
返回值为布尔值 true false

12. 数组的拼接
arr1.concat(arr2, arr3, ...)
不改原数组

13. 查找数组元素 
1) arr.indexOf(数组元素)
从前往后查找,返回第一个符合条件的下标
如果查找不到,返回-1
2) arr.lastIndexOf(数组元素)
从后往前查找,返回后面第一个符合条件的下标
如果查找不到,返回-1

14. 截取数组
arr.slice(startIndex, endIndex)
注意:
截取时含头不含尾
当只有一个参数时,表示从开始位置截取到最后
当开始位置的下标大于结束位置的下标时,返回空数组

15. 增加删除数组元素
1) 尾部操作
增加: arr.push(数字元素1, 数组元素2, ...)
返回数组的长度
删除: arr.pop() 
没有参数,一次只能删除一个数组元素,返回删除的数组元素
2) 头部操作
增加: arr.unshift(数组元素1, 数组元素2, ...)
返回数组的长度
删除: arr.shift()
没有参数,一次只能删除一个数组元素,返回删除的数组元素

16. 增加删除数组元素  改变原数组
arr.splice(startIndex, delCount, 数组元素1, 数组元素2, ...)
返回删除的数组元素,当删除个数为0时,返回空数组
当删除个数为0,新增数组元素时,增加到开始位置索引(startIndex)的前面

17. 分隔数组/分割成字符串
arr.join(分隔符)
默认用逗号分隔 返回string类型

18. 数组排序
arr.sort()
默认升序排列 排序要配合函数使用
升序:
arr.sort(function(a,b){
	return a-b;
});
降序:
arr.sort(function(a,b){
	return b-a;
});

19. 数组翻转
arr.reverse()

20. 累加器
arr.reduce(function(total, currentValue, [currentIndex], [arr]){...}, [initialValue])
total: 初始值,或计算结束后的返回值 必须参数
currentValue: 当前数组元素 从索引0开始 一直循环到最后一个数组元素 必须参数
currentIndex: 当前数组元素对应的数组索引 可选参数
arr: 当前数组元素所在数组对象 可选参数
initialValue: 传递给函数的初始值 可选参数
注意: reduce()方法对于空数组不会执行回调函数

*/
```

## 对象

```js
/*
1. 定义
对象是大括号包含的无序的数组集合
对象由键值对构成,多个键值对之间用逗号隔开,最后一个键值对后面不能加逗号
键值对由键名和键值构成,键名和键值之间用冒号隔开
键名: 键值  {key: value}

2. 作用
存储数据的容器
可以存储多条,且无序

3. 键名
又称为对象的属性
对象的属性默认为string类型,所以加不加引号都可以
以下情况属性必须加引号:
1) 数字开头
2) 包含特殊的符号

4. 键值
键值就是属性所对应的具体的值
键值可以是任何数据类型
当键值是函数时,习惯把属性称为方法

5. 创建对象
1) 字面量法
var obj = {
	属性: 属性值,
	属性1: 属性值1
};

6. 对象的读取
1) 读取
① 点运算符  obj.属性
② []运算符  obj['属性']
2) 写入
① 点运算符  obj.属性 = 属性值
② []运算符  obj['属性'] = 属性值

点运算符和[]运算符的区别:
能用点肯定能用[],能用[]不一定能用点
以下情况必须用[]:
1) 属性命名不规范
2) 当属性为字符串变量时,obj[变量名] 不加引号

7. 对象的遍历
for(var i in obj){
	console.log(obj[i]);
}
注意:
i表示属性名
[]里不加引号
如果属性为字符串变量,不加引号
如果属性为对象中真实存在的属性,加引号

8. 判断对象是否包含某个属性
"属性名" in obj
返回布尔类型 true false

9. 对象的引用
对象赋值以后就绑定在一起,赋值给的是地址

*/
```

## 函数

```js
/*
1. 定义
函数是事件驱动或者被调用才执行的可重复使用的代码块

2. 作用
1) 提高代码的可重用性
2) 提高代码的可维护性
3) 控制执行事件

3. 特点
1) 拥有某种特定功能
2) 可被重复使用
3) 闭合的代码块

4. 创建函数
1) function命令法
function 函数名(参数1, ...){函数体}
2) 函数表达式法
var 变量名 = function(参数, ...){函数体}

5. 函数的调用
函数名(); 
变量名();

6. 函数参数
1) 形式参数 简称形参
形参是定义函数时写在小括号内的参数
不用var 声明
多个形参用逗号隔开

2) 实际参数 简称实参
实参是调用函数时写在小括号内的参数
多个实参用逗号隔开

3) 当形参个数 > 实参个数  多余的形参为undefined (相当于声明变量没有赋值)
当实参个数 > 形参个数  多余的实参直接忽略掉

7. 函数的返回值
return ...;

8. 函数声明提升 
1) function命令法可以在声明之间调用函数
2) 函数表达式法不可以在声明之间调用函数

9. 函数作用域
1) 含义: 作用域是指变量存在的范围
2) 分类
① 全局作用域  全局变量
全局变量在任何位置都可以使用
② 函数作用域  局部变量: 形参/在函数内部且直接用var声明的变量
局部变量只能在函数作用域中使用,在函数作用域外面失效
当局部和全局都有相同变量时,局部先使用自己的变量,自己没有变量时再使用全局变量

*/
```

# 文档对象模型 DOM

## DOM介绍

```js
/*
1. DOM: document object model

2. 作用: 规定了一套管理HTML文档的机制

3. 节点(node): DOM中规定HTML中的一切都称为节点
1) 整个文档称为文档节点
2) 所有元素称为元素节点 (element node)
3) 所有文本称为文本节点 (text node)
4) 所有属性称为属性节点 (attribute node)
5) 所有注释称为注释节点
所有节点之间都有联系: 父节点 子节点 兄弟节点
注意: 属性和元素是兄弟节点

4. document节点
document节点又可以称为document对象
document节点为HTML文档的根节点
只要浏览器一加载,会自动生成document节点

5. document常用的属性
1) 文档的标题
document.title
2) 文档的本地路径
document.location.href

*/
```

## 选中页面元素

```js
/*
1. 通过ID选择
document.getElementById('idName')

2. 通过标签名选择
document.getElementsByTagName("标签名") 返回数组类型

3. 通过className选择
document.getElementsByClassName('className') 返回数组类型

4. 通过css选择器选中页面元素
1) document.querySelector() 获取符合条件的第一个元素
2) document.querySelectorAll() 获取符合条件的所有元素 返回数组类型

*/
```

## 创建页面元素

```js
/*
1. 创建元素
document.createElement('元素名')

2. 创建文本节点
document.createTextNode('文本')

3. 创建属性
document.createAttribute('属性名')

4. 属性赋值
属性.value = '属性值'

5. 设置属性节点
元素.setAttributeNode(属性名)

6. 作为子节点追加到页面
父节点.appendChild(子节点)

*/
eg:
var div = document.createElement('div');
document.body.appendChild(div);
var divText = document.createTextNode('div内容...');
div.appendChild(divText);
var styleAttr = document.createAttribute('style');
styleAttr.value = 'width: 200px;height: 200px;background-color: red;';
div.setAttributeNode(styleAttr);
```

## 操作页面属性

```js
/*
1. 获取元素的属性
ele.getAttribute('属性名')
返回值: 如果有则返回属性值 如果没有则返回null

2. 设置元素的属性
ele.setAttribute('属性名','属性值')

3. 删除元素的属性
ele.removeAttribute('属性名')

*/
```

## 操作style属性

```js
/*
1. ele.style.css属性 = '属性值';
注意:
1) 当css属性用横杠连接,需要去掉横杠,换成驼峰命名法 eg: background-color ==> backgroundColor
2) 当属性为js关键字时,需要在属性前面加css(也是驼峰命名法) eg: float ==> cssFloat
3) css的属性值为string类型,单位不可省略

2. ele.style.cssText = '属性名:属性值;属性名:属性值';

*/
```

## 操作className

```js
/*
var box = document.querySelector('#box');
box.className = 'box';

*/
```

## 事件

```js
/*
1. 作用
可以使页面具有交互性

2. 事件一般配合函数使用

3. 事件的语法
1) 写在HTML中
<标签名 on事件名='js代码'></标签>
2)HTML和js中
HTML:  <标签名 on事件名='调用函数'></标签>
JavaScript:	 定义函数 
3)js中
ele.on事件名 = function(){...}

4. 事件  鼠标按下 ==> 鼠标松开 ==> 鼠标点击
1) 鼠标点击事件 onclick
2) 鼠标移入事件 onmouseenter
3) 鼠标移出事件 onmouseleave
4) 鼠标移入事件 onmouseover
5) 鼠标移出事件 onmouseout
6) 鼠标按下事件 onmousedown
7) 鼠标释放事件 onmouseup
8) 鼠标移动事件 onmousemove
注意: onmouseover和onmouseout支持冒泡 即子元素会继承父元素的这两个事件
onmouseenter和onmouseleave不支持冒泡

*/
```

## 修改页面文本内容

```js
/*
修改页面文本内容
ele.innerHTML = '内容';

*/
```



