title: 关于css3 transition的问题：transition该放在哪？
categories: 前端开发 
tags: [css3] 
description: 附加一段文章摘要，字数最好在140字以内。
date: 2015/11/30 13:29
---

css的transition允许css的属性值在指定时间内平滑地过渡。<!--more-->这种效果可以在鼠标单击、获得焦点、被点击或对元素任何改变中触发，并平滑地以动画效果逐渐改变CSS的属性值。

一般我们使用hover来改变css值

在书写的时候，可能初学者会产生疑惑，不清楚transition是写在普通状态的元素上，还是写在元素的hover状态上，为了清晰直观描述，这里举个栗子，只写关键部分


html：

```html
<div class="demo1">transition放在normal状态</div>
<div class="demo2">transition放在hover状态</div>
```

css：
```css
div{width:100px;height:100px;background:#333;color:#fff;margin:20px}
.demo1{
    -webkit-transition:all 1s ease;
    -moz-transition:all 1s ease;
    -ms-transition:all 1s ease;
    -o-transition:all 1s ease;
    transition:all 1s ease;
}
.demo1:hover{
    background:#ccc;
    color:#333;
    width:200px;
}
.demo2{
    
}
.demo2:hover{
    background:#ccc;
    color:#333;
    width:200px;
    -webkit-transition:all 1s ease;
    -moz-transition:all 1s ease;
    -ms-transition:all 1s ease;
    -o-transition:all 1s ease;
    transition:all 1s ease;
}
```
通过demo可以看到，实际上过渡状态分为两部分，顺向和逆向，即mouseenter和mouseleave产生的动效；当transition放到元素的hover状态时，只会产生顺向的过度动画