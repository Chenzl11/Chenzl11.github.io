---
title: jQuery
toc: true
mathjax: true
categories:
  - jQuery
tags:
  - js
  - jQuery
date: 2020-11-12 21:10:21
summary:
cover:
coverImg:
top:
img:
---

# jQuery

## 简介

```js
/*
什么是jQuery: jQuery是JavaScript的一个库,里面是由JS代码封装好的各种函数,可以利用这些函数实现对页面中元素的操作,如操作css样式,也可以操作从后台获取数据等等.
jQuery的宗旨: 写的更少,做的更多

*/
```

## 使用方式

```js
/*
1. 引入jQuery:
<script src="jQuery地址"></script>

2. jQuery入口函数:
1) 方式1: $(function(){
	...
});
2) 方式2: $(document).ready(function(){
	...
});

3. load事件: JS原生事件 ready事件: jQuery中的事件
区别: 
1) ready事件的触发时间要早于load事件,ready事件实在DOM树渲染完毕后触发,而load事件是在页面中的节点加载完毕后触发,如页面中的图片都加载完毕了才会触发该事件
2) 页面中可以有多个ready事件同时存在,它们不会产生覆盖现象,而load只能有一个,后面加的会覆盖掉前面的.

4. $符号的作用:
它指向了一个函数,就是jQuery的构造函数,它可以用来选取页面中的元素,也可以将DOM对象转换为jQuery对象,还可以用来写入口函数.
注意: jQuery中除了用$代表jQuery的构造函数,还可以用jQuery关键字来代表.即 $ === jQuery.如果项目中有其他的框架里面也有$符号,那么为了避免冲突,我们这时就不要使用$符号,而改用jQuery关键字.

5. DOM对象: 用原生JS的方式获取到的页面元素被称为DOM对象
jQuery对象: 用jQuery的方式获取到的页面元素被称为jQuery对象 
jQuery对象和DOM对象的相互转化:
jQuery对象转化为DOM对象: jQuery对象[下标]
DOM对象转化为jQuery对象: $(DOM对象)

6. 选择器 ===> CSS选择器
注意: 绑定事件中this的使用,需要加上$(this) 转化为jQuery对象才可以使用jQuery的方法
特殊:
:first/:last/:eq(num)/:even/:odd/:lt(num)/:gt(num)/  ==>是按照下标开始找 从0开始
:first-child/:last-child/:nth-child(num)/:nth-last-child(num)/:first-of-type/:last-of-type/:nth-of-type(num)/:nth-last-of-type(num)/   ==>是按照位置开始找 从1开始
表单过滤选择器:
1) :input 过滤所有的输入框
2) :text  过滤所有的文本框
3) :password  过滤所有的密码框
4) :radio  过滤所有的单选框
5) :checkbox  过滤所有的复选框
6) :submit  过滤所有的提交按钮
7) :reset  过滤所有的重置按钮
8) :button  过滤所有的点击按钮
9) :checked 获取选中的元素
10) :selected  获取选中的元素

*/
```

## jQuery常用方法

```js
/*
1. html方法和text方法
text方法
	作用: 获取或设置jQuery对象中的内容
	格式: jQuery对象.text();/jQuery对象.text(内容);
html方法
	作用: 获取或设置jQuery对象中的内容
	格式: jQuery对象.html();/jQuery对象.html(内容);
text方法和html方法的区别:
1) text方法在获取jQuery对象下面内容的时候,返回的是所有文本内容拼接的字符串
2) html方法在获取jQuery对象下面内容的时候,返回的是文本内容和后代节点
3) 在设置内容时,text方法不解析标签,html方法会解析标签
4) 如果jQuery对象由多个元素构成,那么text方法在执行时会隐式迭代,而html方法只取jQuery对象中第一个元素的内容

2. val方法
作用: 获取或设置表单元素的值
格式: 表单元素.val();/表单元素.val(值);

3. attr方法和prop方法: 都可以设置jQuery对象的属性,都可以一次性添加多个属性
区别: attr方法可以设置自定义属性而prop方法不可以设置自定义属性
设置selected/checked属性时一般使用prop方法将属性的值设置为true/false
一次性添加多个属性,格式:
jQuery对象.attr/prop({属性1;:属性值,属性2:属性值, ...});

4. removeAttr方法和removeProp方法: 都可以删除属性,注意removeProp方法是将属性值设置为undefined,一次性删除多个属性用空格隔开

5. css方法: 获取或设置css属性,可以一次性设置多个属性 
jQuery对象.css({属性1: 属性值, 属性2: 属性值, ...})

6. addClass方法、toggleClass方法、removeClass方法
addClass方法: 为jQuery对象添加class属性,可添加多个class jQuery对象.addClass('class1 class2');
toggleClass方法: 为jQuery对象添加class属性,注意: 如果有class则删除,如果没有则添加
removeClass方法: 删除jQuery对象的class jQuery对象.removeClass('class1');

7. 获取或设置jQuery对象的尺寸
1) width()/height(): 不受padding/margin/border/scroll影响,设置时可以加px也可以不加
2) innerWidth()/innerHeight(): 受padding影响,设置时可以加px也可以不加
3) outerWidth()/outerHeight(): 受padding/border影响,设置时可以加px也可以不加

8. 滚动条操作
1) scrollTop(): 获取或设置Y轴滚动条的位置
2) scrollLeft(): 获取或设置X轴滚动条的位置

9. 创建jQuery对象
格式1: $('<div>')
格式2: $('<div>内容</div>')
格式3: $('<div id="box" class="box1">内容</div>')

10. 内部追加jQuery对象的方法 操作已有的节点时都具有移动节点的功能
1) append方法和appendTo方法
作用: 将jQuery对象以尾部追加的方法添加到容器内部
格式: 容器.append(被添加的jQuery对象或标签形成的字符串)  被添加对象.appendTo(代表容器的jQuery对象或选择器)
2) prepend方法和prependTo方法
作用: 将jQuery对象以开头追加的方式添加到容器内部
格式: 容器.prepend(被添加的jQuery对象或标签形成的字符串)  被添加对象.prependTo(代表容器的jQuery对象或选择器)

11. 外部追加jQuery对象的方法 操作已有的节点时都具有移动节点的功能
1) after方法和insertAfter方法
作用: 在目标元素的后面插入新的jQuery对象
格式: 目标元素.after(要插入的新的jQuery对象)  要插入的新的jQuery对象.insertAfter(目标元素)
2) before方法和insertBefore方法
作用: 在目标元素的前面插入新的jQuery对象
格式: 目标元素.before(要插入的新的jQuery对象)  要插入的新的jQuery对象.insertBefore(目标元素)

12. 删除节点的方法
1) empty方法
作用: 清空某个容器下面的所有内容
格式: 容器.empty();
2) remove方法
作用: 删除页面中的某个jQuery对象
格式: 要被删除的jQuery对象.remove('选择器');
注意: 如果被删除元素的身上有事件,那么事件会被删除
eg: 
$('#box').remove(); //表示删除id为box的元素
$('li').remove('#box'); //表示删除带有id=box的li标签元素

13. 克隆节点
clone方法
作用: 克隆页面中的元素
格式: 要被克隆的元素.clone(true/false) false为默认值,表示不克隆事件 true表示克隆事件
返回值: 被克隆出来的节点

14. 获取祖先元素的方法
1) parent方法
作用: 返回父节点
格式: 当前节点.parent();
2) parents方法
作用: 返回所有的祖先节点
格式: 当前节点.parents();
3) parentsUntil方法
作用: 获取到某个祖先节点之前的祖先节点,不包含该节点
格式: 当前节点.parentsUntil('祖先节点2'); //返回值中不包含祖先节点2

15. 获取后代节点的方法
1) children方法
作用: 返回被选元素的所有直接子元素
格式: 当前元素.children();
2) find方法
作用: 返回被选元素的后代元素
格式: 当前元素.find();
eg: $('#box').find('span'); //返回id为box的元素内部的所有span元素

16. 获取兄弟元素的方法 不包含本身
1) siblings方法: 获取所有的兄弟元素
2) next方法: 获取后一个兄弟元素
3) nextAll方法: 获取后面所有的兄弟元素
4) nextUntil方法: 获取到后面第几个元素位置的兄弟元素 eg: $('#li5').nextUntil('#li9');//li标签从6-8
5) prev方法: 获取前一个兄弟元素
6) prevAll方法: 获取前面的所有兄弟元素
7) prevUntil方法: 获取到前面的第几个元素位置的兄弟元素 eg: $('#li5').prev('#li2');//li标签从3-4

17. jQuery对象的过滤 返回的都是jQuery对象
1) first方法: 返回被选中元素的首个元素
2) last方法: 返回被选中元素的最后一个元素
3) eq方法: 返回被选中元素中带有指定索引的元素
4) filter方法: 过滤出指定选择器的jQuery对象,选择器之间用逗号隔开

18. 其他
1) addBack方法: 将目标元素添加到jQuery对象集合中 eg: $('#box').nextAll().addBack();
2) end方法: 返回链式结构被破坏之前的那个jQuery对象 eg: $('#box').next().end();


*/
```

## jQuery事件

```js
/*
1. jQuery事件的添加方式
1) 方式1 格式: 
jQuery对象.事件名称(function(){
	//事件被触发时要执行的操作
});
注意: 如果同一元素被添加多个相同的事件,事件不会覆盖

2) 方式2 格式: 
//绑定一个事件
jQuery对象.bind('事件名称', function(){
	//事件被触发时要执行的操作
});
//绑定多个事件,对应的操作相同
jQuery对象.bind('事件名称1, 事件名称2, ...', function(){
	//事件被触发时要执行的操作
});
//绑定多个事件,对应操作不相同
jQuery对象.bind({
	事件名称1: function(){},
	事件名称2: function(){},
	...
});
//在为元素绑定事件的时候,给它传递数据
jQuery对象.bind('事件名称', {属性1: 属性值, 属性2: 属性值, ...}, function(e){
	//使用事件对象的data属性来获取传递进来的数据
	var data = e.data;
});

3) 方式3 格式: 
祖先元素.delegate(后代元素, 事件名称, 数据, function(){
	//事件被触发时要执行的操作
});
注意: 该方法在为元素绑定事件时只能用事件委托的形式来绑定

4) 方式4 格式: 
jQuery对象.on('事件名称', function(){});
jQuery对象.on('事件名称1 事件名称2 ...', function(){});
jQuery对象.on({
	事件名称1: function(){},
	事件名称2: function(){},
	...
});
祖先元素的jQuery对象.on('事件名称', '后代元素', 数据, function(){});

特殊: 
1) hover方法
作用: 为元素添加移入和移出事件
格式: jQuery对象.hover(function(){},function(){}); //前一个方法表示移入事件,后一个方法表示移出事件
2) one方法
作用: 给元素添加一次性事件
格式: jQuery对象.one('事件名称', function(){});

2. jQuery事件的删除方式
1) unbind方法
作用: 删除jQuery对象身上的事件(一般是删除通过bind方法绑定的事件)
格式1: jQuery对象.unbind();//表示删除所有事件
格式2: jQuery对象.unbind('事件名称');//表示删除指定事件
2) undelegate方法
作用: 删除通过delegate方法绑定的事件
格式: jQuery对象.undelegate();
3) off方法
作用: 删除事件(任何方式添加的事件都可以删除)
格式1: jQuery对象.off();//表示删除所有事件
格式2: jQuery对象.off('事件名称');//表示删除指定事件

*/
```

## jQuery中的内置动画

```js
/*
1. 显示与隐藏
1) hide方法: 隐藏动画 格式: jQuery对象.hide(动画执行所需时间, function(){});//动画执行完毕触发的方法 
1) show方法: 显示动画 格式: jQuery对象.show(动画执行所需时间, function(){});//动画执行完毕触发的方法 
1) toggle方法: 隐藏/显示动画 格式: jQuery对象.toggle(动画执行所需时间, function(){});//动画执行完毕触发的方法 

2. 滑动(向上/向下)
1) slideDown方法: 向下滑动 格式: jQuery对象.slideDown(动画执行所需时间, function(){});//动画执行完毕触发的方法 
2) slideUp方法: 向上滑动 格式: jQuery对象.slideUp(动画执行所需时间, function(){});//动画执行完毕触发的方法 
3) slideToggle方法: 向上/下滑动 格式: jQuery对象.slideToggle(动画执行所需时间, function(){});//动画执行完毕触发的方法 

3. 淡入与淡出
1) fadeIn方法: 淡入 格式: jQuery对象.fadeIn(动画执行所需时间, function(){});//动画执行完毕触发的方法
2) fadeOut方法: 淡出 格式: jQuery对象.fadeOut(动画执行所需时间, function(){});//动画执行完毕触发的方法
3) fadeToggle方法: 淡入/淡出 格式: jQuery对象.fadeToggle(动画执行所需时间, function(){});//动画执行完毕触发的方法
4) fadeTo方法: 将元素的透明度逐渐改变到指定的值,注意即使设置元素的透明度为0,元素也是占位的,因为元素没有被设置display:none;
格式: jQuery对象.fateTo(动画执行所需时间, 设置透明度);

*/
```

## jQuery中的自定义动画

```js
/*
1. animate方法
作用: 用来创建自定义动画的方法
格式: jQuery对象.animate(参数1, 参数2, 参数3, 参数4);
参数说明:
	参数1: 该参数通常是一个对象,里面以键值对的形式封装了要达到的CSS样式 注意: animate的修改样式时只对属性值中包含数值的样式敏感,属性值可以不带单位
	参数2: 动画执行所需的时间,单位为毫秒,该参数也可以是字符串,如fast(200ms)、normal(400ms)、slow(600ms) 注意: 如果是任意字符串,即表示的是normal
	参数3: 动画在执行时的状态(匀速、慢-快-慢) 只支持两个值 linear、swing(默认) 注意:设置该参数时要加引号
	参数4: 回调函数,动画执行完毕后执行该回调函数
	
2. stop方法
作用: 停止动画
格式: jQuery对象.stop(参数1, 参数2);
参数说明:
	 参数1: 值为布尔值,默认值为false(结束当前动画,执行下一次动画),如果为true(结束当前动画,清空动画队列,即删除剩余动画)
	 参数2: 值为布尔值,默认值为false(当前动画没有完成,开始执行下一次动画),如果为true,表示立即完成当前动画,并完成队列(即完成其他动画)

*/
```

## each方法

```js
/*
each方法
作用: 可以利用each方法对jQuery对象集合中的每个元素做单独的处理
格式: jQuery对象.each(function(index, ele){
	//在函数内部可以对jQuery对象集合中的每个对象做单独的处理
});
回调函数参数说明:
	index: jQuery对象集合中DOM对象的下标
	ele: 集合中的DOM对象

*/
```

## $.each方法

```js
/*
$.each方法
作用: 该方法是$的一个静态方法,可以用该方法去处理数组或对象
格式: $.each(数组/对象, function(index, val){});

*/
```

