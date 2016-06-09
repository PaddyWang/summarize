# canvas

> PaddyWang

### 绘制形状

##### 流程

*   创建一个画布 -> `<canvas>`
*   设置画布的尺寸 -> `width/height`
    -   默认尺寸 300 X 150
    -   不带单位
    -   不要在 style 中设置，直接设置属性
*   选择绘画工具
*   绘制路径
*   填充/描边

##### 绘制环境 context

*   获取绘图上下文
    -   **canvasElem.getContext(2d)**
*   绘制路径
    -   **moveTo(x, y)**
    -  ** lineTo(x, y)**
    -   **closePath()**  -> *将起点与终点连接起来*
    -   **rect(x, y, w, h)** -> *绘制矩形路径*
    -   **arc(x, y, r, startDeg, endDeg, [是否逆时针])** -> *绘制弧形路径*
    -   **beginPath()** -> *开启新的路径*
*   渲染函数
    -   **stroke()** -> *描边*
    -  ** fill()** -> *填充*
    -   **strokeRect(x, y, w, h)** -> *直接渲染矩形，对路径不造成影响*
    -   **fillRect(x, y, w, h)**  -> *不影响路径*
    -   **clearRect(x, y, w, h)** -> *清空画布*
*   渲染样式
    -   **strokeStyle**
    -   **lineWidth**
    -   **fillStyle**

### 绘制文本

*   渲染函数  *原点默认在文字的左下方*
    -   **strokeText(text, x, y)**
    -   **fillText(text, x, y)**
*   渲染样式
    -   **font** -> *'font-size font-family'*
    -   **textAlign** -> *'start | end | center | left | right ' - 文本水平对齐方式*
    -   **textBaseLine** -> *'top | middle | bottom'  - 文本基线对齐方式，即垂直对齐方式*
    -   对齐方式基于原点为参考系，当左对齐的时候，即原点在文字左侧
    -   所有的样式值为字符串类型

### 绘制图像

##### **drawImage**

*   三参数
    -   **drawImage(imgElem, dx, dy)**
    -   dx/dy : 目标坐标，即绘制在画布上的坐标
*   五参数
    -   **drawImage(imgElem, dx, dy, dw, dh)**
    -   dw/wy : 绘制在画布上尺寸
*   九参数
    -   **drawImage(imgElem, sx, sy, sw, sh, dx, dy, dw, dh)**
    -   sx/sy : 在图像上的切割坐标 ; sw/sh : 在图像上的切割尺寸

### 扩展

*   canvas 抗锯齿

     由于描边的时候会出现矩形现象，于是进行了颜色透明淡化处理，

     于是在后面再渲染路径时就会出现颜色叠加现象

*   **requestAnimationFrame(fn)**  *请求动画帧*

    不用写时间间隔

    由浏览器决定什么时候绘制下一帧

    现在的浏览器一般在 16.667 毫秒，在浏览器性能差的时候可能时间比这长

    60 HZ  -> 16.667 = 1000 / 60


*   绘制直线的小bug
    
    在进行moveTo和lineTo绘制直线，此时的直线是以2像素来显示的

    并且是以灰色显示的

    因为浏览器在进行渲染的时候进行了处理

    **解决办法：**

    1> 用矩形来代替，设置矩形的高或宽为1像素

    2> moveTo(0, 10.5)  lineTo(300, 10.5)

*   上传图像

    获取上传的图像信息：

    `imgData = file.files[0];`

    `url = URL.createObjectURL(file.files[0]);`

    获取画布中指定的图片信息：

    `url = ctx.getImageData(x, y, w, h);`、
