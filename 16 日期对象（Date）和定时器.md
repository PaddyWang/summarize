# 日期对象（Date）和定时器

### 日期对象（Date）

*   日期对象创建
    -   `var date = new Date();`
        +   本地当前日期
        +   `=> Fri Jan 29 2016 11:01:20 GMT+0800 (中国标准时间)`
    -   `var date = new Date("2016/01/29 00:00:00");`
        +   指定的日期
        +   `=> Fri Jan 29 2016 00:00:00 GMT+0800 (中国标准时间)`
*   日期对象方法

|方法|说明
|------|-----
| `getDate();` | 获取天（1-31） 
|`getDay();`|获取星期（0-6）0代表周天
|`getFullYear();`|获取完整年份
|`getMonth();`|获取月份（0-11）1月份从0开始
|`getHours();`|获取小时
|`getMinutes();`|获取分钟
|`getSeconds();`|获取秒钟
|`getMilliseconds();`|获取毫秒（1s=1000ms）
|` getTime();`|获取累计毫秒数（从1970/01/01 00:00:00:000算起）

*   获取累计毫秒数
    -   `var sumMs1 = Date.now();`
    -   `var sumMs2 =+new Date();`
    -   `var sumMs3 = new Date().getTime(); ` （最常用）
    -   `var sumMs4 = new Date().valueOf();`

### 定时器

*   循环定时器
    -   `setInterval(fun,1000);`
    -   `setInterval("fun()",1000);`
    -   `setInterval(function(){  },1000);`
*   一次性定时器（炸弹定时器）
    -   `setTimeout(fun,1000);`
*   清除定时器
    -   `clearInterval(timer);`
    -   `clearTimeout(timer);`
        +   timer:要清除的定时器名