---
date: 2016-12-29 16:33
status: public
title: cookie
---

* 大小4k字节 4096字节
* 就是一些存储在计算机里的字符串
* 结构式键值对的形式
* cookie不能跨浏览器访问
* 按域名存储
* 两种类型的cookie
    * 临时性的cookie
    * 指定生存周期的cookie
    
**cookie的设置**
临时性的cookie：document.cookie="aa=bb";
指定生存周期的cookie：document.cookie="aa=bb;expires="+nowtime.toGMTString();