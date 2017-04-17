# layout
issue
##
浮动元素容器的clearing问题

1.添加空元素
``html
   <div>
        <div style="float:left;width:45%;"></div>
        <div style="float:right;width:45%;"></div>
   </div>
``
父容器现在必须考虑非浮动子元素的位置，而后者肯定出现在浮动元素下方，所以显示出来，父容器就把所有子元素都包括进去了。
违背了语义化的原则

2.浮动的父容器
``html
<div style="float:left;">
    <div style="float:left;width:45%;"></div>
    <div style="float:right;width:45%;"></div>
</div>
``
父容器也改成浮动定位，这样它就可以带着子元素一起浮动
会影响到后面元素的定位，而且有时候因为需要父元素无法变成浮动
