# HTML编码规范

## 1、头部声明


### [强制]使用 `HTML5` 的 `doctype` 来启用标准模式，建议使用大写的 `DOCTYPE`
示例:
```
<!DOCTYPE html>
```

### [建议]启用 IE Edge 模式
示例:
```
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```
解释:  
Edge 模式通知 Windows Internet Explorer 以最高级别的可用模式显示内容

### [建议] 在 html 标签上设置正确的 lang 属性
示例:
```
<html lang="zh-CN">
```
解释:  
有助于提高页面的可访问性，如：让语音合成工具确定其所应该采用的发音，令翻译工具确定其翻译语言等

### [强制] 页面必须使用精简形式，明确指定字符编码。指定字符编码的 meta 必须是 head 的第一个直接子元素
示例:
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        ......
    </head>
    <body>
        ......
    </body>
</html>
```

### [建议]`HTML`文件使用无`BOM `的`UTF-8`编码
解释:  
UTF-8 编码具有更广泛的适应性,BOM 在使用程序或工具处理文件时可能造成不必要的干扰

### [强制]引入 `CSS` 时必须指明 `rel="stylesheet"`
示例:
```
<link rel="stylesheet" href="demo.css">
```

### [建议]引入 `CSS` 和 `JavaScript` 时无须指明 `type` 属性
解释:  
`text/css` 和 `text/javascript` 是 type 的默认值。

### [建议]在 `head` 中引入页面需要的所有 `CSS` 资源，`JavaScript` 应当放在页面末尾，或采用异步加载
示例:
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <link rel="stylesheet" href="test.css">
        ......
    </head>
    <body>
        ......
        <script src="test.js"></script>
    </body>
</html>
```
解释:  
在页面渲染的过程中，新的CSS可能导致元素的样式重新计算和绘制，页面闪烁;将 script 放在页面中间将阻断页面的渲染。出于性能方面的考虑，如非必要，请遵守此条建议。

### [建议] 移动环境或只针对现代浏览器设计的 Web 应用，如果引用外部资源的 `URL` 协议部分与页面相同，建议省略协议前缀
示例:
```
<img src="https://www.xxx.com/logo.png" alt="" /> 
<img src="//www.xxx.com/logo.png" alt="" /> //推荐使用这种写法
```
解释:  
省略URL的协议声明，浏览器照样可以正常引用相应的资源，这项解决方案称为`protocol-relative URL`，暂且可译作 协议相对 URL。如果当前的页面是通过HTTPS协议来浏览的，那么网页中的资源也只能通过HTTPS协议来引用，否则IE浏览中就会出现"页面同时包含安全和非安全的项目"的警告信息；如果使用协议相对 URL，无论你是使用HTTPS，还是HTTP访问页面，浏览器都会以与你相同的协议请求页面中的资源，避免弹出这样的警告信息，同时可以节省5字节的数据量。
需要注意的是：在IE7 / IE8中，使用 <link> 或者 @import 来引用样式表时，会出现样式表文件被下载两次的情况。除了这点，协议相对 URL都是可以正常工作的。

### [强制] 页面必须包含 `title` 标签声明标题，且必须作为 `head` 的直接子元素，并紧随 `charset` 声明之后
示例:
```
<head>
    <meta charset="UTF-8">
    <title>页面标题</title>
</head>
```
解释:  
title 中如果包含 ascii 之外的字符，浏览器需要知道字符编码类型才能进行解码，否则可能导致乱码

### [强制] 保证 `favicon` 可访问
示例:
```
<link rel="shortcut icon" href="path/to/favicon.ico">
```
解释:  
在未指定 favicon 时，大多数浏览器会请求 Web Server 根目录下的 favicon.ico 。为了保证favicon可访问，避免404，必须遵循以下两种方法之一：  

1. 在 Web Server 根目录放置 favicon.ico 文件。  
2. 使用 link 指定 favicon。  
