---
date: 2017-01-09 16:04
status: public
title: jquery
---

**jquery核心理念**
> write less. do more

**特点**
* 小、快、功能丰富
* 跨平台和可拓展
* 隐式循环 --each封装循环
* 链式调用 --this指针，指向jquery
* github
* [] 表示参数可传可不传
* jQuery的入口是

##核心
**jQuery([sel,[context]])--核心函数**

* $里面可以传入字符串类型的选择器(标签) dom对象 html,回调函数
* 可以传入dom对象，jquery对象，字符串类型的选择器
* 标了下标不再是jQuery对象，而是dom对象 $(".div")[0]
* 将dom对象转化成jquery对象 
    
```javascript
//dom对象转为jquery
$(function(){
var obj=document.getElementById('box'))
$(obj)
```
     jquery对象转为dom对象 加下标/get(index)
     dom对象转为jquery对象 加$
 
 **jQuery(html,[ownerDocument])--核心函数**    
```javascript
$("<div>",{
}).appendTo(document.body)
```

**jQuery(callback)--核心函数**
```javascript
//页面结构加载完毕运行
$(document).ready(function(){
)
//页面资源加载完毕
window.onload()
```

**get([index])--对象访问**
```javascript
//将jquery对象转为dom对象
//不传参数将jquery集合转为dom集合
//传入参数和加下标的结果一样
//index可以传入负数,从-1开始
$(".div").get()
```

**index([selector|element])--对象访问**
```javascript
//返回一个元素在一个集合里的索引
    //若返回-1：①元素不在集合里 ②顺序反了
//一般集合在前，要获取元素的选择器在后
$(".div").index($("#sel"))
//也可接收dom对象，jquery对象
$(".div").index($(document.getElementById("sel"))
//当前元素在同辈(同级)元素里的位置
$("#sel").index()
```

**data([key],[value])--缓存数据**
```javascript
//data添加的属性一定不会添加到dom身上
//给每一个jquery对象绑定(用data设置)一个属性：aa=bb 用data去访问
var obj=$(".div");
obj.data{"aa","bb"};
console.log(obj.eq(0).data("aa"));
//用dom的方式访问，返回undefined
console.log(obj.get(0).aa)
//所以要用dom的方式访问
console.log(obj.get(0).data("aa"))
//两个值是设置。一个值是获取
//可以直接调用eq()--可以理解为下标,也可以不用eq,直接写data，默认访问的是第一个
$(".div").data("aa","bb")
console.log($(".div").data("aa"))
```
##选择器
**first-of-child**
修饰的是前面的
**first-of-type**
标签类型相同
**:nth-child**
从1开始

```javascript
console.log($(".box:nth-child(2)")
```

**:nth-of-type(n|even|odd|formula)**
```javascript
console.log($(".box:nth-of-type(2n/2n+1)")
```

**:only-child**
唯一的子元素

**:animated--匹配所有正在执行动画效果的元素**
**:gt(index)--大于**
**:lt(index)--小于**
```javascript
$(".div:lt(3)").animate({width:500},2000)
$(":button")[0].onclick=function(){
	$(".div:animated").css("background","teal")
}
```

**:focus--匹配当前获取焦点的元素**
```javascript
$(".text").get(0).focus()
	$(".text:focus").eq(0).val("加上的")
	$(".text:focus").each(function(index,dom){
		dom.value="新添加的"
	})
```

**:contains()**
```javascript
console.log($(".div:contains(2)").get(0))
```

**:has()**
```javascript
console.log($(".div:has(p)")[0])
```

**:first-child**
```javascript
console.log($(".div:first-child").html())
```
##属性

**attr--可设置可获取**
* 默认获取集合里的第一个元素
* 四种设置方式

```javascript
//1.()
//2.
//3.
//4.
```

**prop--设置标准属性**

**removeClass**
* 传值：只移除所传值对应的
* 不传值：移除所有

**html()**
* 不传值：表示获取
* 传值：表示设置(可传入标签)
    * 也可传回调函数
    
```javascript
    $(".div").html("<b>b标签</b>")
    $(".div").html(function(index,val){
    })
```
    
##CSS

**position()  offset()**
* 和原生的相同，且两者一样，均对可见元素有效
* 但position会将margin算作盒子的一部分

**innerHeight()**
* 获取第一个匹配元素内部区域高度（包括补白-padding、不包括边框）

**outerHeight()**
* 获取第一个匹配元素外部高度（默认包括补白和边框）
* outerHeight(true)计算边距在内

```javascript

```
##文档处理
**append() prepend()**
* 是添加在父元素内部的
* 父元素.append(要添加的元素)
* 要添加的元素.appendTo(父元素)

**after() before**
* 是与父元素同级的
* 父元素.after(要添加的元素)

**insertAfter() insertBefore()**
* 要添加的元素.insertAfter(父元素)

**wrap()**
* wrap()用后边的包住前面的
* unwrap() 不传参数
* wrapAll() 后边包住前边

**replaceWith（）replaceAll()**
* replaceWith()用后边替换前面的
* replaceAll()用前面替换后面所有选中的

**clone()**
* clone() 不传参 不克隆本节点身上的函数 默认只克隆元素-包括子元素
* true 两个true与一个true相同--复制本节点和子节点以及其函数
* false 不传参和false是一样的
*（true,false）只想复制本节点，以及本节点的函数
* 第一个参数：本节点身上的数据和事件能否被拷贝
* 第二个参数：子元素身上的数据和事件能否被拷贝

##筛选

* 筛选和选择器
    * 筛选：从集合挑出--改变this指针，破坏性操作
    * 选择器：一步到位
    
```javascript
$
$('.box:eq(0)').css()--选择器
```

**children()**
* 不传参数 默认会返回每一个匹配元素的子元素组成的jquery集合

**find()**


**closest()--事件委派**
* 从当前元素开始，一级一级向上匹配，直到找到为止，找不到返回空的jquery对象
* 从本身开始往上找，若本身是要找的，则返回本身，找到即停止

**parents()**
* 从父级元素一级一级开始往上找，找到所有的这种类型的元素才停止

**addback()**


**end()**
回到上一次破坏性操作之前

##事件

**on()--注意click的位置**
* on是事件的核心，是所有事件的基础，所有事件借助on实现
* 调用on方法绑定事件
* 同时绑定多个事件，加空格
* 可以实现事件委派

```javascript
//实现事件委派
//可以传入选择器--为父元素的子元素、后代元素
$(document.body).on("click","div",function(){
})
```
* 可以在事件发生时传入一些数据

```javascript
$("div").on("click",{aa:"bb"},function(e){
    console.log(e.data.aa)
})
```

**off()**
* off可以移除事件--获取到事件处理函数才可以删除

```javascript
function aa(e){alert(1)}
$("div").on("click",{aa:"bb"},aa)
$("div").off("click",aa)
```
**bind()**
* on分离出来的

**delegate()--事件委派-注意click的位置**
* 父元素委派子元素

```javascript
$("div").delegate(".one","click",function(){
    alert(1)
})
```

**focusin()**

```javascript      
$("div").focusin(function(){
    $(this).find("input").val("获取焦点")
})

```

**stop()--清空队列**
* 不传参 停止当前队列动画，继续队列后续动画
* 第一个参数 决定是否清空队列 true false
* 第二个参数 决定是否立即完成动画

**finish**
* 不传参 立即完成所有动画，到最后一个状态

**clearQueue**