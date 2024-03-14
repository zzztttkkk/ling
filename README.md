# ling

一种Web Site的“新”思路的实现，不使用“响应式”的渲染框架，依然使用之前很流行的服务器模板渲染。在渲染模板时，收集所有的`script`和`style`块，然后合并起来。

例如，这样的html
``` html
<script src="a0.js" sync></script>
<div id="a1">
</div>
<script src="a1.js"></script>
<div>
</div id="a2">
<script src="a2.js"></script>
<div id="a3">
</div>
<script src="a3.js"></script>
```
会被合并为
``` html
<div id="a1">
</div>
<div id="a2">
</div>
<div id="a3">
</div>
<script src="/merged.js?files=a1&files=a2&files=a3"></script>
```
由服务器来合并它们。

这样可以做到简单的问题简单解决。

