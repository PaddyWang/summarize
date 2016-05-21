# 移动Web开发

### viewport
*用于承载页面的视口，可以进行网页的缩放*

**viewport**（视口）就相当于一张照片纸，浏览器窗口就相当于一个相框，网页就相当于照片上的图案。viewport又不局限于浏览器可视区域的大小，它可能比浏览器的可视区域要大，也可能比浏览器的可视区域要小。在默认情况下，一般来讲，移动设备上的viewport都是要大于浏览器可视区域的，这是因为考虑到移动设备的分辨率相对于桌面电脑来说都比较小，所以为了能在移动设备上正常显示那些传统的为桌面浏览器设计的网站，移动设备上的浏览器都会把自己默认的viewport设为980px或1024px。

*   width：宽度设置的是viewport宽度，可以设置device-width特殊值
    -   `width = device-width`
*   initial-scale：初始缩放比，大于0的数字
    -   `initial-scale = 1.0`
*   maximum-scale：最大缩放比，大于0的数字
    -   `maximum-scale = 1.0`
*   minimum-scale：最小缩放比，大于0的数字
    -   `minimum-scale = 1.0`
*   user-scalable：用户是否可以缩放，yes或no（1或0）
    -   `user-scalable = no`

**移动端开发 标准模式：**

    <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0">

### 样式处理
*   清除点击高亮
    -   `-webkit-tap-highlight-color:transparent;`
    -   *在移动端浏览器会遇见点击出现高亮的效果，在某项项目是不需要这个默认的效果的。那么我们通常会把这个点击的颜色设置成透明。*

*   所有盒子以边框开始计算
    -    `-webkit-box-sizing: border-box;`
    -    `box-sizing: border-box;`
    -    *在移动端通常使用的是百分比布局，那么这样的布局如果使用了border或者padding，就会导致容器的宽度超出屏幕的宽度从而产生滚动条。解决方案是：用css3属性 box-sizing设置所有的盒子从边框开始计算宽度。*
*   Input清除默认的样式
    -   `border: none;`
    -   `outline: none;`
    -   `-webkit-appearance: none;`
    -   *在移动设备上的浏览器中，表单一般会有默认的属性。通过`border:none;outline:none;`是无法完全清除的，还是会有一些浏览器默认的属性，比如：内阴影，立体感......可以通过`-webkit-appearance`这个属性指的是设置成`none`，来完全清除*
*   最小宽度和最大宽度的限制
    -   `max-width: 640px;  /*在行业当中的移动端的设计图一般使用的是640px*/`
    -   `min-width: 300px;  /*在移动设备当中现在最小的尺寸320px*/`
    -   *适用于图片比较多的首页，门户，电商 等*
    -   *作用 ：保证页面在尺寸比较大的设备当中，页面的效果也就是清新度不会受到太大影响，以及页面在小尺寸的设备当中有较好的布局效果。*
*   Img的下间隙问题
    -   1.`display: block;`
    -   2.`font-size:0;`
    -   *文字基线默认的 baseline 是以字母X的下边开始计算的*
    -   *Img是行内块级元素它也会有默认的基线对齐。那么和文字一样也会距离底部有一定的间隙。*
*   搜索按钮调用
    -   ```<form action=""><input type="search" placeholder="提示"/>
</form>```
    -   *在移动端调用输入法的时候会弹出小键盘，键盘一般是enter键，那么在搜索框当中我们要求调用是搜索按钮，那么这样的结构才能调用出来。*
*   全屏单页面布局
    -   `/*满屏*/ html,body{height: 100%;}`
*   两栏：其中一栏宽度固定，一栏自适应
    -   1.固定宽度盒子绝对定位;自适应盒子width:100% + padding
    -   2.文本环绕：固定盒子浮动；自适应盒子overflow:hidden;

### 移动端事件

*在移动端不支持on事件，通过addEventListener添加事件*

*   Touch事件
    -   **touchstart**：当手指触碰屏幕时触发
        +   `dom.addEventListener('touchstart',function(e){});`
    -   **touchmove**：当手指在屏幕上滑动时连续触发
        +   `dom.addEventListener('touchmove',function(e){});`
    -   **touchend**：当手指离开屏幕时触发
        +   `dom.addEventListener('touchend',function(e){});`
*   事件返回e对象所包含的基本属性
    -   **targetTouches** 目标元素的所有当前触摸
    -   **changedTouches** 页面上最新更改的所有触摸 
    -   **touches** 页面上的所有触摸
        +   **clientX**:  触摸目标在视口中的X坐标
        +   **clientY**:  触摸目标在视口中的Y坐标
        +   **pageX**：触摸目标在页面中的x坐标
        +   **pageY**：触摸目标在页面中的y坐标
        +   **screenX**:  触摸目标在屏幕中的x坐标
        +   **screenY**:  触摸目标在屏幕中的y坐标
        +   ***在touchend事件的时候event只会记录changedtouches***


*   过渡和动画结束事件
    -   **transitionEnd**  过渡结束后触发
        +   `dom.addEventListener('webkitTransitionEnd',function(e){ });`
        +   `dom.addEventListener('transitionEnd',function(e){ });`
    -   **animationEnd**  动画结束后触发
        +   `dom.addEventListener('webkitAnimationEnd',function(e){ });`
        +   `dom.addEventListener('animationEnd',function(e){ });`

####   学习网站
*   动画网站：<a href="https://daneden.github.io/animate.css/">https://daneden.github.io/animate.css/</a>
    -   *这个网站可以提供一些常用的动画，可以在做移动开发的时候可以参考这个网站的效果完成动画*
*   Zepto：<a href="http://zeptojs.com/">http://zeptojs.com/</a>
    -   *Zepto是一个轻量级的针对现代高级浏览器的JavaScript库， 它与jquery有着类似的api。 如果你会用jquery，那么你也会用zepto*
*   Weiui：<a href="http://weui.github.io/weui/">http://weui.github.io/weui/</a>
    -   *微信UI库，它是微信前端团队提供给广大的微信开发者的一些ui组件库。方便开发这开发出和微信风格一致的 内嵌应用*