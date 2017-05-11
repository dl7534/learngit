---
date: 2017-02-13 09:18
status: public
title: js基础
---

**JavaScript**
基于 对象 和事件驱动 的解释性 松散型 语言
**javascript的作用**
1、数据验证
2、将动态的内容写入到页面中
3、对事件进行响应
4、读写html内容
5、检测浏览器各项属性
6、创建cookie
7、模拟动画
**JavaScript组成部分**
1、ECMAscript  基础语法
2、BOM		 浏览器对象模型
3、DOM		 文档对象模型
**引入方式**
1、嵌入方式
2、外部方式
3、超链接 重定向
```javascript
<a href="javascript:alert('我是链接');">弹出a</a>
```
重定向
```javascript
<form action="javascript:alert('我是表单')">
	<input type="text" name="">
	<input type="submit">	
</form>
```
4、事件调用
```javascript
<div style="width:200px; height:200px; background:orange;" onclick="alert('i am')"></div>
```
**变量**
* 1、区分大小写
var AA =2;
* 2、_ $ 字母      开头
     _ $ 字母 数字 中间或者结尾
var _aa;
var $aa;
* 3、可以放入任何数据
var aa =true;
var aa =[];
var aa =function() {};
* 4、变量名要有意义
* 5、不能用关键字、保留字做名字
	// var function 
* 6、变量覆盖
var b =1;
var b ='a';
alert(b);
* 7、不用var声明的变量
	* 1）不赋值就报错
	* 2）赋值变成全局变量
* 用var声明的变量
	1) 如果一个变量被重新声明而没有赋值，值不变
	2) 一个变量只声明不赋值，默认是undefined
   c = '1';
   alert(c);
* 8、驼峰命名法
   manPeople