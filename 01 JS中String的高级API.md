# JS中String的高级操作
### String（高级API）

*   字符串索引操作

    -   charAt()
    
            指定索引位置字符 = str.charAt(index);

    -   charCodeAt()
     
            指定索引位置字符ASCII = str.charCodeAt(index);

    -   indexOf()
     
            指定字符的索引 = indexOf(chr);
                // 从前开始查找第一个指定字符

    -   lastIndexOf()
    
            指定字符的索引 = lastIndexOf(chr);
                // 从后查找

*   字符串截取操作

    -   concat()
        
            newStr = str1.concat(str2);
                // 将字符串2添加到字符串1后面，并返回新字符串

    -   slice()
    
            newStr = str.slice(3,6);
                // 截取两个索引之间的字符串[包左不包右）
                // （两个参数都代表索引）

            newStr = str.slice(3);
                // 截取指定索引到最后的字符串

            newStr = str.slice(-3);
                // 截取最后三位字符串

            newStr = str.slice(6,3);
                // 返回空

    -   substr()
    
            newStr = str.substr(3,6);
                // 截取从索引3向后6位字符串
                // （第一个参数代表索引，第二个参数代表截取长度）

            newStr = str.substr(3);
                // 截取指定索引到最后的字符串

            newStr = str.substr(-3);
                // 截取最后三位字符串

    -   substring()
    
            newStr = str.substring(3,6);
                // 截取两个索引之间的字符串[包左不包右）
                // （两个参数都代表索引）

            newStr = str.substring(3);
                // 截取指定索引到最后的字符串

            newStr = str.substring(-3);
                // 截取整个字符串

            newStr = str.substring(6,3);
                // 智能转换成（3,6）

*   编码解码

    -   encodeURIComponent()
    
            enStr = encodeURIComponent(str);
                // 编码

    -   decodeURIComponent()
    
            str = decodeURIComponent(enStr);
                // 解码

*   大小写转换

    -   toUpperCase()
    
            STR = str.toUpperCase();
                // 小写转换成大写

    -   toLowerCase()
    
            str = STR.toLowerCase();
                // 大写转换成小写
