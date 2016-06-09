### 字体图标

> PaddyWang

*   引用字体包
```
    \@font-face {
        font-family: 'font-name';
        /*引入字体文件  不同的浏览支持的字体文件的格式不一样*/
        src: url(fonts/MiFie-Web-Font.eot) format('embedded-opentype'),
             url(fonts/MiFie-Web-Font.svg) format('svg'),
             url(fonts/MiFie-Web-Font.ttf) format('truetype'),
             url(fonts/MiFie-Web-Font.woff) format('woff');
    }
```
*   定义类样式
```
    .wjs-icon {
        font-family: 'font-name';
    }
    .wjs-icon-phone::before {
        content: '\e908';
    }
```

*   引用图标

    `<span class="wjs-icon wjs-icon-phone"></span>`

