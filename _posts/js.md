---
layout: post
title: "Jquery的相关知识点"
subtitle: 'Jquery knowledge'
author: "Zhao"
header-style: text
tags:
  - Vim

---

# 一.JQuery特性

## 1.jquery是什么？

jQuery 是一个 JavaScript 库。jQuery 极大地简化了 JavaScript 编程。jQuery 库可以通过一行简单的标记被添加到网页中。

## 2.它的优势：

- 轻量级、体积小，使用灵巧(只需引入一个`js`文件
- 强大的选择器
- 出色的`DOM`操作的封装
- 出色的浏览器兼容性
- 可靠的事件处理机制
- 完善的`Ajax`
- 链式操作、隐式迭代
- 方便的选择页面元素(模仿`CSS`选择器更精确、灵活)
- 动态更改页面样式/页面内容(操作`DOM`，动态添加、移除样式)
- 控制响应事件(动态添加响应事件)
- 提供基本网页特效(提供已封装的网页特效方法)
- 快速实现通信(`ajax`)
- 易扩展、插件丰富

## 3.jquery有哪些功能（API）？

- 选择器
- 过滤器
- 事件
- 效果
- ajax

# 二.JQuery知识点

## 1.基础选择器

（1）. $("button").attr("disabled","true"); --使按钮变灰，不可用状态


（2）. $("*");  --它的功能是获取页面中的全部元素


（3）. $("form *").attr("disabled", "true"); --将<form>元素包含下的全部表单型元素都设为不可用。


（4）. $("ance desc");层次选择器，ance参数（ancestor祖先的简写）表示父元素；desc参数（descendant后代的简写）表示后代元素，即包括子元素、孙元素等等。两个参数都可以通过选择器来获取。


（5）. $(“parent > child”); child参数获取的元素都是parent选择器的子元素，它们之间通过“>”符号来表示一种层次关系。


（6）. $(“prev + next”);其中参数prev为任何有效的选择器，参数“next”为另外一个有效选择器，它们之间的“+”表示一种上下的层次关系，也就是说，“prev”元素最紧邻的下一个元素由“next”选择器返回的并且只返回唯的一个元素。


（7）.$(“prev ~ siblings”);其中参数prev与siblings两者之间通过“~”符号形成一种层次相邻的关系，表明siblings选择器获取的元素都是prev元素之后的同辈元素。(获取prev 元素后面全部相邻的元素)

## 2.过滤选择器

（1）. :first过滤选择器 --:first过滤选择器的功能是获取第一个元素，常常与其它选择器一起使用，获取指定的一组元素中的第一个元素。
:last过滤选择器 是获得最后一个元素
（2）. :eq(index);--从一组标签元素数组中，灵活选择任意的一个标签元素,其中参数index表示索引号（即：一个整数），它从0开始，如果index的值为3，表示选择的是第4个元素。
（3）. :contains(text)选择器;功能是选择包含指定字符串的全部元素，它通常与其他元素结合使用，获取包含“text”字符串内容的全部元素对象。其中参数text表示页面中的文字。


（4）. :has(selector)过滤选择器;--功能是获取选择器中包含指定元素名称的全部元素，其中selector参数就是包含的元素名称，是被包含元素。


（5）. :hidden过滤选择器的功能是获取全部不可见的元素，这些不可见的元素中包括type属性值为hidden的元素。


（6）. :visible过滤选择器获取的是全部可见的元素，也就是说，只要不将元素的display属性值设置为“none”，那么，都可以通过该选择器获取。
（7）. [attribute=value]属性选择器的功能是获取与属性名和属性值完全相同的全部元素，其中[]是专用于属性选择器的括号符，参数attribute表示属性名称，value参数表示属性值。
（8）. [attribute*=value]，它可以获取属性值中包含指定内容的全部元素，其中[]是专用于属性选择器的括号符，参数attribute表示属性名称，value参数表示对应的属性值。


（9）. :first-child子元素过滤选择器则可以获取每个父元素中返回的首个子元素，它是一个集合，常用多个集合数据的选择处理。
:last-child 子元素过滤选择器则可以获取每个父元素中返回的最后一个子元素，它是一个集合

## 3.表单选择器

（1）. :input表单选择器  :input;--功能是返回全部的表单元素，不仅包括所有<input>标记的表单元素，而且还包括<textarea>、<select> 和 <button>标记的表单元素，因此，它选择的表单元素是最广的。
（2）. :text表单文本选择器 --可以获取表单中全部单行的文本输入框元素，单行的文本输入框就像一个不换行的字条工具，使用非常广泛。
（3）. :password选择器，它的功能是获取表单中全部的密码输入文本框元素。
（4）. :radio单选按钮选择器
（5）. :checkbox复选框选择器
（6）. :submit提交按钮选择器
（7）. :image图像域选择器
（8）. :button表单按钮选择器
（9）. :checked选中状态选择器
（10）.  :selected选中状态选择器

## 4.jQuery 操作DOM元素

(1). appendTo()方法也可以向指定的元素内插入内容，它的使用格式是：$(content).appendTo(selector)参数content表示需要插入的内容，参数selector表示被选的元素，即把content内容插入selector元素内，默认是在尾部。


(2). 调用clone()方法可以生成一个被选元素的副本，即复制了一个被选元素，包含它的节点、文本和属性，它的调用格式为：$(selector).clone() 其中参数selector可以是一个元素或HTML内容。


(3). replaceWith()和replaceAll()方法都可以用于替换元素或元素中的内容，但它们调用时，内容和被替换元素所在的位置不同，分别为如下所示：$(selector).replaceWith(content)和$(content).replaceAll(selector) 参数selector为被替换的元素，content为替换的内容。


(4). wrap()和wrapInner()方法都可以进行元素的包裹，但前者用于包裹元素本身，后者则用于包裹元素中的内容，它们的调用格式分别为：
$(selector).wrap(wrapper)和$(selector).wrapInner(wrapper)参数selector为被包裹的元素，wrapper参数为包裹元素的格式。

(5). 使用each()方法可以遍历指定的元素集合，在遍历时，通过回调函数返回遍历元素的序列号，它的调用格式为：$(selector).each(function(index))参数function为遍历时的回调函数，index为遍历元素的序列号，它从0开始。


(6). remove()方法删除所选元素本身和子元素，该方法可以通过添加过滤参数指定需要删除的某些元素，而empty()方法则只删除所选元素的子元素。

## 5.jQuery 事件与应用

(1). ready()事件类似于onLoad()事件，但前者只要页面的DOM结构加载后便触发，而后者必须在页面全部元素加载成功才触发，ready()可以写多个，按顺序执行。此外，下列写法是相等的： $(document).ready(function(){})等价于$(function(){});


(2). $(selector).bind(event,[data] function) --参数event为事件名称，多个事件名称用空格隔开，function为事件执行的函数。


(3). 使用hover()方法切换事件,hover()方法的功能是当鼠标移到所选元素上时，执行方法中的第一个函数，鼠标移出时，执行方法中的第二个函数，实现事件的切实效果，调用格式如下：$(selector).hover(over，out); over参数为移到所选元素上触发的函数，out参数为移出元素时触发的函数。

(4). 使用toggle()方法绑定多个函数,toggle()方法可以在元素的click事件中绑定两个或两个以上的函数，同时，它还可以实现元素的隐藏与显示的切换，绑定多个函数的调用格式如下：$(selector).toggle(fun1(),fun2(),funN(),...);其中，fun1，fun2就是多个函数的名称.


(5). 使用unbind()方法移除元素绑定的事件,unbind()方法可以移除元素已绑定的事件，它的调用格式如下：$(selector).unbind(event,fun);其中参数event表示需要移除的事件名称，多个事件名用空格隔开，fun参数为事件执行时调用的函数名称。


(6). 使用unbind()方法移除元素绑定的事件,unbind()方法可以移除元素已绑定的事件，它的调用格式如下：$(selector).unbind(event,fun);其中参数event表示需要移除的事件名称，多个事件名用空格隔开，fun参数为事件执行时调用的函数名称。如果没有规定参数，unbind() 方法会删除指定元素的所有事件处理程序。


(7). 使用one()方法绑定元素的一次性事件,one()方法可以绑定元素任何有效的事件，但这种方法绑定的事件只会触发一次，它的调用格式如下：$(selector).one(event,[data],fun);参数event为事件名称，data为触发事件时携带的数据，fun为触发该事件时执行的函数。


(8). 调用trigger()方法手动触发指定的事件,trigger()方法可以直接手动触发元素指定的事件，这些事件可以是元素自带事件，也可以是自定义的事件，总之，该事件必须能执行，它的调用格式为：$(selector).trigger(event);其中event参数为需要手动触发的事件名称。


(9).文本框的focus和blur事件,focus事件在元素获取焦点时触发，如点击文本框时，触发该事件；而blur事件则在元素丢失焦点时触发，如点击除文本框的任何元素，都会触发该事件。
(10). 下拉列表框的change事件,当一个元素的值发生变化时，将会触发change事件，例如在选择下拉列表框中的选项时，就会触change事件。
(11). 调用live()方法绑定元素的事件,与bind()方法相同，live()方法与可以绑定元素的可执行事件，除此相同功能之外，live()方法还可以绑定动态元素(比如：动态添加的元素)，即使用代码添加的元素事件，格式如下：$(selector).live(event,[data],fun);参数event为事件名称，data为触发事件时携带的数据，fun为触发该事件时执行的函数。(注意：从 jQuery 1.7 开始，不再建议使用 .live() 方法。1.9不支持.live())

## 6.jQuery 动画特效

(1). 调用show()和hide()方法显示和隐藏元素 --show()和hide()方法用于显示或隐藏页面中的元素，它的调用格式分别为：$(selector).hide(speed,[callback])和$(selector).show(speed,[callback]);参数speed设置隐藏或显示时的速度值，可为“slow”、“fast”或毫秒数值，可选项参数callback为隐藏或显示动作执行完成后调用的函数名
(2). 调用toggle()方法就可以很容易做到，即如果元素处于显示状态，调用该方法则隐藏该元素，反之，则显示该元素，它的调用格式是：$(selector).toggle(speed,[callback]);其中speed参数为动画效果时的速度值，可以为数字，单位为毫秒，也可是“fast”、“slow”字符，可选项参数callback为方法执行成功后回调的函数名称。


(3). 使用slideUp()和slideDown()方法的滑动效果--可以使用slideUp()和slideDown()方法在页面中滑动元素，前者用于向上滑动元素，后者用于向下滑动元素，它们的调用方法分别为：$(selector).slideUp(speed,[callback])和$(selector).slideDown(speed,[callback]);其中speed参数为滑动时的速度，单位是毫秒，可选项参数callback为滑动成功后执行的回调函数名。(要注意的是：slideDown()仅适用于被隐藏的元素；slideup()则相反。)


(4). 使用slideToggle()方法实现图片“变脸”效果--使用slideToggle()方法可以切换slideUp()和slideDown()，即调用该方法时，如果元素已向上滑动，则元素自动向下滑动，反之，则元素自动向上滑动，格式为：$(selector).slideToggle(speed,[callback]);其中speed参数为动画效果时的速度值，可以为数字，单位为毫秒，也可是“fast”、“slow”字符，可选项参数callback为方法执行成功后回调的函数名称。


(5). 使用fadeIn()与fadeOut()方法实现淡入淡出效果--fadeIn()和fadeOut()方法可以实现元素的淡入淡出效果，前者淡入隐藏的元素，后者可以淡出可见的元素，它们的调用格式分别为：$(selector).fadeIn(speed,[callback])和$(selector).fadeOut(speed,[callback]);其中参数speed为淡入淡出的速度，callback参数为完成后执行的回调函数名。

(6). 使用fadeTo()方法设置淡入淡出效果的不透明度--调用fadeTo()方法，可以将所选择元素的不透明度以淡入淡出的效果调整为指定的值，该方法的调用格式为：$(selector).fadeTo(speed,opacity,[callback]);其中speed参数为效果的速度，opacity参数为指定的不透明值，它的取值范围是0.0~1.0，可选项参数callback为效果完成后，回调的函数名。

(7). 调用animate()方法制作简单的动画效果--调用animate()方法可以创建自定义动画效果，它的调用格式为：$(selector).animate({params},speed,[callback])其中，params参数为制作动画效果的CSS属性名与值，speed参数为动画的效果的速度，单位为毫秒，可选项callback参数为动画完成时执行的回调函数名。


(8). 调用stop()方法停止当前所有动画效果--stop()方法的功能是在动画完成之前，停止当前正在执行的动画效果，这些效果包括滑动、淡入淡出和自定义的动画，它的调用格式为：$(selector).stop([clearQueue],[goToEnd]);其中，两个可选项参数clearQueue和goToEnd都是布尔类型值，前者表示是否停止正在执行的动画，后者表示是否完成正在执行的动画，默认为false。


(9). 调用delay()方法延时执行动画效果 --delay()方法的功能是设置一个延时值来推迟动画效果的执行，它的调用格式为：$(selector).delay(duration);其中参数duration为延时值，它的单位是毫秒，当超过延时值时，动画继续执行。

## 7.jQuery 实现Ajax应用

(1). 使用load()方法异步请求数据--使用load()方法通过Ajax请求加载服务器中的数据，并把返回的数据放置到指定的元素中，它的调用格式为：load(url,[data],[callback])参数url为加载服务器地址，可选项data参数为请求时发送的数据，callback参数为数据请求成功后，执行的回调函数。


(2).使用getJSON()方法异步加载JSON格式数据--使用getJSON()方法可以通过Ajax异步请求的方式，获取服务器中的数组，并对获取的数据进行解析，显示在页面中，它的调用格式为：jQuery.getJSON(url,[data],[callback])或$.getJSON(url,[data],[callback]);其中，url参数为请求加载json格式文件的服务器地址，可选项data参数为请求时发送的数据，callback参数为数据请求成功后，执行的回调函数。


(3).使用getScript()方法异步加载并执行js文件--使用getScript()方法异步请求并执行服务器中的JavaScript格式的文件，它的调用格式如下所示：jQuery.getScript(url,[callback])或$.getScript(url,[callback]);参数url为服务器请求地址，可选项callback参数为请求成功后执行的回调函数。


(4). 使用get()方法以GET方式从服务器获取数据--使用get()方法时，采用GET方式向服务器请求数据，并通过方法中回调函数的参数返回请求的数据，它的调用格式如下：$.get(url,[callback]);参数url为服务器请求地址，可选项callback参数为请求成功后执行的回调函数。


(5). 使用post()方法以POST方式从服务器发送数据--与get()方法相比，post()方法多用于以POST方式向服务器发送数据，服务器接收到数据之后，进行处理，并将处理结果返回页面，调用格式如下：$.post(url,[data],[callback]);参数url为服务器请求地址，可选项data为向服务器请求时发送的数据，可选项callback参数为请求成功后执行的回调函数。


(6). 使用serialize()方法序列化表单元素值--使用serialize()方法可以将表单中有name属性的元素值进行序列化，生成标准URL编码文本字符串，直接可用于ajax请求，它的调用格式如下：$(selector).serialize();其中selector参数是一个或多个表单中的元素或表单元素本身。(调用表单元素本身的serialize()方法，将表单中元素全部序列化，生成标准URL编码，各元素间通过&号相联。)


(7). 使用ajax()方法加载服务器数据 --使用ajax()方法是最底层、功能最强大的请求服务器数据的方法，它不仅可以获取服务器返回的数据，还能向服务器发送请求并传递数值，它的调用格式如下：jQuery.ajax([settings])或$.ajax([settings]);其中参数settings为发送ajax请求时的配置对象，在该对象中，url表示服务器请求的路径，data为请求时传递的数据，dataType为服务器返回的数据类型，success为请求成功的执行的回调函数，type为发送数据请求的方式，默认为get。

(8). 使用ajaxSetup()方法设置全局Ajax默认选项--使用ajaxSetup()方法可以设置Ajax请求的一些全局性选项值，设置完成后，后面的Ajax请求将不需要再添加这些选项值，它的调用格式为：jQuery.ajaxSetup([options])或$.ajaxSetup([options]);可选项options参数为一个对象，通过该对象设置Ajax请求时的全局选项值。


## 8.this 和 $(this) 的区别？

\$(this)是jquery对象，能调用jquery的方法，例如click(), keyup()。
而this,则是html元素对象，能调用元素属性，例如this.id,this.value。
例如假设已经使得this和\$(this)都指向了input对象了，若要获得input的值,可以this.value，但\$(this)就得$(this).val()。

## 9.ready 和 onload 的区别？

页面加载完成有两种事件：
一是ready，表示文档结构（DOM结构）已经加载完成（不包含图片等非文字媒体文件），
二是onload，指示页面包含图片等文件在内的所有元素都加载完成。(可以说：ready 在onload 前加载！！！)

ready可以绑定多个事件，onload会覆盖前面的事件。

我的理解： 一般样式控制的，比如图片大小控制放在onload 里面加载;而：jS事件触发的方法，可以在ready 里面加载;

## 10.同步和异步的区别？

open()方法的参数3，用于控制 是否同异步。

默认参数为true，表示请求是异步的，AJAX不会影响到其他程序的执行。

参数为false，表示请求是同步的，AJAX将阻塞之后程序的运行，直到响应完全接受完毕为止。