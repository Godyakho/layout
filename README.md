# layout
clearfix issue
##
常见的清除浮动的相关问题

1.父元素加overflow：hidden
```html
 .father{
         overflow:hidden
 }
 .fl{
      background: #000;
      height: 100px;
      width: 100px;
      float: left;
 }
    <div class="father">
        <div class="fl"></div>
        <div class="fl"></div>
    </div>
```
父元素overflow:hidden后，首先会计算height: auto的真实高度，由于其触发了BFC，需要包含子元素，所以高度不是0，而是子元素高度。<br />
•overflow的值不为visible。<br />
•display的值为table-cell, table-caption, inline-block中的任何一个。<br />
•position的值不为relative和static<br />
都可以出发BFC<br />
不支持ie6，且当父盒子小于子盒子的大小时会出现问题。<br />

2.伪类
```html
        .clearfix:after {
            content: "\0020";
            display: block;
            height: 0;
            clear: both;
        }
        .clearfix {
            zoom: 1;
        }
    <div class="clearfix">
        <div class="fl"></div>
        <div class="fl"></div>
    </div>
```

3.clear：both
```html
     <div>
        <div class="fl"></div>
        <div class="fl"></div>
        <div style="clear: both"></div>
    </div>
 ```
 增加无意义的标签，不符合语义化。
 
 4.父元素一起浮动float
 ```html
 .father{
        float:left
 }
 .fl{
      background: #000;
      height: 100px;
      width: 100px;
      float: left;
 }
    <div class="father">
        <div class="fl"></div>
        <div class="fl"></div>
        <div style="clear: both"></div>
    </div>
    ```
    影响后面元素的定位
