---
date: 2016-12-20 07:24
status: public
title: node
---

* 节点
    * html是文档的根节点
    * 节点的关系：父节点 兄弟节点 子节点
    * 直接的父节点只有一个
* HTML文档节点的分类
    * 元素节点(标签)
    * 文本节点
    * 属性节点
    * 注释节点
    * 文档节点（document）
* 所有的节点，以及节点之间的相互关系构成了我们整个html的文档树模型
* 节点的属性
    * nodeType  节点类型
    * nodeValue 节点值
    * nodeName  节点名字

|节点种类|nodeType|nodeValue|nodeName|
|:---:|:---:|:---:|:---:|
|元素节点| 1 | null | 大写的标签名 |
|文本节点| 3 | 文本的内容(文本值--包含空格) | #text |
|属性节点| 2 | 属性值 | 属性名 |
|注释节点| 8 | 注释内容 | #comment |
|文档节点| 9 | null | #document |
* 节点的关系
    * childNodes 节点的所有子节点
    * parentNode 父节点
    * firstChild 第一个子节点
    * lastChila 最后一个子节点
    * nextSibling 下一个兄弟节点
    * previousSibling 上一个兄弟节点


```javascript
<body>
	<div class="box">
		我是文本
	</div>
	<p class="bor">
		fefe
		<!-- 我是注释 -->
	</p>
</body>
<script>
	//元素节点
	var div=document.getElementsByClassName('box')[0];
	console.log(div.nodeType)
	console.log(div.nodeValue)
	console.log(div.nodeName)
	//文本节点
	var div=document.getElementsByClassName('box')[0];
	var text=div.childNodes[0];
	console.log(text.nodeType)
	console.log(text.nodeValue)
	console.log(text.nodeName);

	//注释节点
	var p=document.getElementsByClassName('bor')[0];
	var text=p.childNodes[1];
	console.log(text.nodeType);   //8           节点类型
	console.log(text.nodeValue);  //我是注释    节点值
	console.log(text.nodeName);   //#comment    节点名字 

	//文档节点
	console.log(document.nodeType)
	console.log(document.nodeValue)
	console.log(document.nodeName)

</script>
```