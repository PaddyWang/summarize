### 1、历史管理

>* history对象
>
>    -  `history.back();`     *// 后退*
>    
>    -  `history.forward();`  *// 前进* 
>    
>    -  `history.go(n);`     *// 前进/后退n步*
>    
>    -  `history.length;`     *// 历史条数*
>    
>    -  `pushState(data,title,url);`  *// 追加一条历史记录*
>
>    -  `onpopstate`  *// 当前进/后退时触发  调用者 window  （浏览器上的按钮）*
   
**example：**

          var btn = document.getElementById('btn');     
           btn.onclick = function(){
               history.pushState({name:'haha'},'title','demo.html');
           }
           window.onpopstate = function(e){
               console.log(e.state);    // Object {name: "haha"}
           }

### 2、Web存储

>*  document.cookie  *// 存储数据上限4K*
>
>*   sessionStorage   *// 5M*
> 
>    - `window.sessionStorage.setItem(key,val);` *//设置值*
>
>    - `window.sessionStorage.getItem(key);`   *//读取值*
>
>    - `window.sessionStorage.removeItem(key);` *//删除值*
>
>    - `window.sessionStorage.clear();`         *//清空值*
>
>    **// 生命周期为：关闭页面**
>
>    **// 数据共享仅限于本页面使用**
>
>*   localStorage  *// 20M*
>
>    *// 用法同上session*
>
>    **// 永久生效  除非手动清除**
>
>    **// 数据跨页面共享使用**

**example：**

        // 设置
        document.querySelector('.set').onclick = function(){
            window.sessionStorage.setItem(this.parentNode.querySelector('.key').value,this.parentNode.querySelector('.val').value);
        }
        // 获取
        document.querySelector('.get').onclick = function(){
            this.parentNode.querySelector('.val').value = window.sessionStorage.getItem(this.parentNode.querySelector('.key').value);
        }
        // 删除
        document.querySelector('.remove').onclick = function(){
            window.sessionStorage.removeItem(this.parentNode.querySelector('.key').value);
        }
        // 清空
        document.querySelector('.clear').onclick = function(){
            window.sessionStorage.clear();
        }

###  3、应用缓存

##### H5轻松创建离线应用  只需要添加一个.appcache文件即可
>*  第一步
>   -   缓存清单：  文件后缀 => .appcache

>*  第二步
>   -   文件顶行 => CACHE MANIFEST

>*  第三步
>   -   CACHE:    *# 列出需要缓存的内容*

>   -   NETWORK:  *# 指定需要在线访问的资源*

>   -   FALLBACK: *# 当缓存的资源找不到时进行替换*

>*  第四步应用

>   -   在将要缓存的页面添加 => `<html manifest="src" >`

>*  第五步更新

>   -   # version 1.0.1 
 
>    *# 自定义版本号 通过改变注释里的内容 重新缓存*

**example：**

    CACHE MANIFEST

    #通过改变活注释内容，达到缓存清单内容发生更改，进而重新缓存资源
    # version 1.0.7

    #指定需要在线访问的资源
    NETWORK:

    ./js/main.js

    #列出需要缓存的内容
    CACHE:

    ./images/img1.jpg
    ./images/img2.jpg
    ./images/img3.jpg
    ./images/img4.jpg
    ./images/img5.jpg

    #指定需要在线访问的资源
    NETWORK:

    ./js/main1.js

    # 当缓存的资源找不到的情况，会自动替换FALLBACK里的内容
    # 如 ./online.html找不到了，则会替换成 ./offline.html
    FALLBACK:

    ./css/online.css ./css/offline.css
    ./online.html ./offline.html
