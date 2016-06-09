# DOM操作

> PaddyWang

### DOM节点访问
*   获取节点
    -   **getElementById()**
        +   `一个节点 = document.getElementById(id)`
    -  ** getElementsByClassName()**
        +  `节点数组 = document.getElementsByClassName(class)`
    -  ** getElementsByTagName()**
        +  `节点数组 = document.getElementsByTagName(tag)`
    -  ** querySelector()**
        +  `一个节点 = document.querySelector(selector)`
    -  ** querySelectorAll()   **
        +  `节点数组 = document.querySelector(selector)`
*   访问父节点
    -   **parentNode**
        +   `父节点 = 子节点.parentNode;`
*   访问兄弟节点
    -   **nextElementSibling**
    -   **nextSibling**
        +   `下一个兄弟节点 = 节点.nextElementSibling || 节点.nextSibling;`
    -   **previousElementSibling**
    -   **previousSibling**
        +   `前一个兄弟节点 = 节点.previousElementSibling || 节点.previoudSibling;`
*   访问子节点
    -   **firstElementChild**
    -   **firstChild**
        +   `第一个子节点 = 父节点.firstElementChild || 父节点.firstChild;`
    -   **lastElementChild**
    -   **lastChild**
        +   `最后一个子节点 = 父节点.lastElementChild || 父节点.lastChild;`
    -   **children**
        +   `子节点数组 = 父节点.children;`
    -   **childNodes**
        +   `子节点数组 = 父节点.childNodes;`


**总结:**

*   访问任何节点
    -   `节点本身.parentNode.children[index];`
*   可以通过`nodeType`判断是什么节点
    -   1 : `element`标签节点
    -   2 : `attribute`属性节点
    -   3 : `text`文本节点
    -   8 : `comment`注释节点
    -   9 : `document`文档节点
### DOM节点操作

*   创建节点
    -   **createElement()**
        +   `新节点 = document.creatElement(要创建的节点);`
*   添加节点
    -   **appendChild()**
        +   `父节点.appendChild(节点);`
        +   在父节点最后插入一个节点
    -  ** insertBefore()**
        +   `父节点.insertBefore(节点,参考节点); `
        +   在参考节点之前插入节点
*   删除节点
    -   **removeChild()**
        +   `父节点.removeChild(节点);`
        +   删除父节点内指定的子节点（必须指定子节点）
*   复制节点
    -   **cloneNode()**
        +    `新节点 = 节点.cloneNode(true/false);`
        +    `false`：浅复制（不填默认`false`）
        +    `true`：深复制
*   属性节点操作
    -   **getAttribute()**
        +   `属性值 = 节点.getAttribute("属性");`
        +   获取指定属性值
    -   **setAttribute()**
        +   `节点.setAttritube(属性,值);`
        +   修改或添加属性值
    -   **removeAttribute()**
        +   `节点.removeAttribute(属性);`
        +   删除指定属性

**总结:**

*   自己删除自己
    -   `节点本身.parentNode.removeChild(节点本身);`