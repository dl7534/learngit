---
date:
status: public
title: window
---

## window  对象 是BOM的顶层对象
  **location对象**
  **history对象**
  **document对象**
* window对象的属性和方法
    * alert(document.documentElement.clientWidth)    获取浏览器的宽度
    * alert(document.documentElement.clientHeight)   获取浏览器的高度
    * alert(window.screen.width)                     屏幕分辨率的宽度
    * alert(window.screen.height)                    屏幕分辨率的高度
```javascript
var width=document.documentElement.clientWidth;
console.log(width);
```
   * 时间函数
     * setInterval()     开始进程时间函数，每隔一定时间运行一次  返回时间函数id
     * clearInterval()   结束时间函数
     * setTimeout()      开始时间函数，只运行一次  返回时间函数id
     * clearTimeout()    结束时间函数
        * 进程：实现某一功能的程序的一次运行活动
        * 一个进程可以有多个线程
        * 进程可以被计算机分配资源（Cook）
        * 线程之间可以资源共享，相互通讯（shucai） 
            
## location
* location.href()   获取完整路径  
* 协议      域名/主机名    端口号   路径    锚地址   查询字符串
* protocol  host/hostname   port  pathname   hash     search
    * https 网络传输协议（安全）
    * http  网络传输协议
    * file  本地文件传输协议
    * ftp   邮件传输协议
* location.assign()
* location.replace()不会留下历史记录
* location.reload()参数可以是一个布尔类型，如果是true，将会绕过缓存，重新从服务器加载数据。
    
## history
* history.length()    返回历史记录的长度
* history.back()    加载历史记录的上一个
* history.forward()    加载历史记录的下一个
* history.go(n)    0刷新  1加载历史记录的下一个  -1加载历史记录的上一个