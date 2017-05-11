---
date: 2017-01-05 15:56
status: public
title: ajax
---


**ajax是什么**
> ajax是异步的javascript和XML
主要用来无刷新的获取数据

##同步异步

* html 超文本标记语言 显示信息
* XML  是可扩展的标记语言 存储信息

**实例化构造函数创建ajax对象--兼容处理**
```javascript
var ajax=new XMLHttpRequest();
var ajax=new ActiveXObject("Microsoft.XMLHTTP)--IE低版本
```

**去做什么**
open 打开请求
* ajax.open("get","地址","同步异步--默认true异步","")
* method,URL,asynch,user,pass
```javascript
ajax.open("get","login.php?aa=bb＆cc=dd","true","user")
```
   
    
**走**
send 发送请求
```javascript
ajax.send(null)
```

**监测**
```javascript
//存储函数
ajax.onreadystatechange=function(){
//打开是否成功
if(ajax.readyState==4){
//数据是否正确    
     if(ajax.status==200){
     console.log(ajax.responseText)
        }
    }
}
```
**post方式**
地址放在send中--键值对
```javascript
ajax.setRequestHeader("Content-Type","application/x-www-form-urlencoded")
```

**post和get的区别**
get 拿 post 送
相同点：两者都可以传送数据
不同点
post 传送数据，那么在send里面传送
get  在地址栏传送
post比get更安全
get 传送的数据量一般是比较小的
post 传送稍微大的数据

**XML**
```javascript
//引号分号要包住内容
$xml="<?xml version='1.0' encoding='utf8'?>";

//例子
//php中
$xml="<?xml version='1.0' encoding='utf8'?>
		<clothes>
			<header>头部</header>
			<footer>底部</footer>
		</clothes>
		";
echo $xml;
//html中
var xml=ajax.responseXML;
console.log(xml);
var head=xml.getElementsByTagName('header');
console.log(head);
```

**json**
```javascript
//字符串
//将符合js语法规范的字符串语言解析成js代码用eval
//php中
echo '{"aa":"bb","cc":"dd"}'  
//html中
var result=ajax.response;
console.log(result);
console.log(eval("("+result+")"));

```
**解码--兼容火狐**
```javascript
//加分号
//若是xml,html要改成xml
header("Content-Type:text/html;charset=utf8");
```

**数据库语句**
* 查 
```javascript
select 字段 from 表名 where查询的条件
```
* 增 
```javascript
insert into 表名（字段） values(字段值)
```
* 删
```javascript
delete from 表名 where 删除的条件
```
* 改
```javascript
update  表名 set （字段=字段值） where更新的条件
```

****
onreadystatechange
readyState
response
responseText
responseXML
status