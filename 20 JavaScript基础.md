# JavaScript基础

> PaddyWang

*   JavaScript 包含： `ECMAScript、DOM和BOM`。
*   JavaScript 的基本类型有 ：`string、number、boolean`。
*   JavaScript 的复合类型有 ：`String、Number、Boolean、Date、Array、Math、RegExp`，还有两个核心类型：`Object和Function`。
*   JavaScript 还有两个空类型 ：`null和undefined`。
*   JavaScript 中获得类型的运算符是 ：`typeof`。 使用该运算符返回什么数据类型?boolean。
*   JavaScript 中 === 和 == 有什么区别? 
    -   === ：类型和值都得相等
    -   == ：只要值相等就行
*   JavaScript 中 in 运算符有什么用? 
    -   查询一个对象中是否包含某个属性
    -   `'name' in obj`  返回boolean值
*   JavaScript 的条件运算符是：
*   JavaScript 中创建对象使用new运算符。
*   JavaScript 什么叫逻辑中断：短路函数
    -   表达式1 || 表达式2
    -   表达式1为true，则忽略表达式2
    -   表达式1为false，则再执行表达式2
*   JavaScript 中 delete 运算符的作用是
    -   返回：boolean
    -   语法：delete data
    -   1、删除数组中的一个元素`delete arr[3]`
    -   2、删除一个对象的属性或方法`delete obj.name`
    -   3、删除一个没有用var声明的变量`delete str`

>       var n = 1;
>       m = 2;
>       var delete1 = delete n;
>       var delete2 = delete m;
>       console.log(delete1);  // => false
>       console.log(delete2);  // => true
>       console.log(n);  // => 1
>       console.log(m);  // => 报错 ：m is not defined  // 报错会终止代码执行

*   JavaScript 中循环语句有3种. 分别是：`for、for in、while、do while`
*   JavaScript 中分支语句有2种. 分别是: ____, ____.
*   JavaScript 中跳转语句 break 与 continue 如何使用
    -   break ：跳出整个循环
    -   continue ：跳出本次循环，继续执行下次
