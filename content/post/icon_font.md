+++
date = "2016-03-01T00:00:00+08:00"
title = "字符图标的使用"
description = ""
tags = ["CSS"]
topics = ["CSS"]
+++

{{% img src="/media/iconfont-ycon.png" alt="logo" class="third right hid" %}}
在网页中展示图片,除了引用图片文件外,还可以通过使用字符图标达到类似的效果.  
通过将图标存储为字体,可以很容易的进行缩放,改变颜色,通过CSS装饰.  
记录一下使用css引用字符图标的相关方法.

<!--more-->


**使用公开的图标库 如[Font awesome][1]**  
---

---
  
下载对应的字体和css文件,放到static目录下  
引用font-awesome-4.5.0.min.css  
```
<link rel="stylesheet" href="/static/css/font-awesome-4.5.0.min.css">
```

想要使用图标时,首先找到对应的类名,然后在模板中插入,如<i aria-hidden="true" class="fa fa-modx"></i>
```
<i aria-hidden="true" class="fa fa-modx"></i>
```

**使用[iconfont平台][2]管理和制作个人图标库**
---

---

首先在AI中制作好图标,然后根据说明导出SVG文件上传至平台  
引用上传的图标,创建新项目,然后下载字体文件到本地static目录  
参考Demo创建相关的css文件并引用
```
@font-face {
	font-family: 'yea978-1';
	src:url('../fonts/yea978-1.eot');
	src:url('../fonts/yea978-1.eot?#iefix') format('embedded-opentype'),
		url('../fonts/yea978-1.woff') format('woff'),
		url('../fonts/yea978-1.ttf') format('truetype'),
		url('../fonts/yea978-1.svg#yea978-1') format('svg');
	font-weight: normal;
	font-style: normal;
}
.icon-yea978-1 {
	font-family: 'yea978-1';
    font-size:15em;
	speak: none;
	font-style: normal;
	font-weight: normal;
	font-variant: normal;
	text-transform: none;
	line-height: 1;
	-webkit-font-smoothing: antialiased;
}
.icon-yea978-1:before {
	content: "\e600";
}
```
使用自己的图标在模板中替换原图标
```
<div class="icon-yea978-1" id="logo"></div>
```

[1]:http://fortawesome.github.io/ "http://fortawesome.github.io/" 
[2]:http://www.iconfont.cn/ "http://www.iconfont.cn/" 