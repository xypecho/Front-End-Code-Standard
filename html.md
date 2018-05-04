# HTML编码规范

### 1、头部声明


#### [强制]使用 `HTML5` 的 `doctype` 来启用标准模式，建议使用大写的 `DOCTYPE`
示例:
```
<!DOCTYPE html>
```

#### [建议]启用 IE Edge 模式
示例:
```
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```
解释:
Edge 模式通知 Windows Internet Explorer 以最高级别的可用模式显示内容

#### [建议] 在 html 标签上设置正确的 lang 属性
示例:
```
<html lang="zh-CN">
```
解释:
有助于提高页面的可访问性，如：让语音合成工具确定其所应该采用的发音，令翻译工具确定其翻译语言等

#### [强制] 页面必须使用精简形式，明确指定字符编码。指定字符编码的 meta 必须是 head 的第一个直接子元素
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

#### [建议]`HTML`文件使用无`BOM `的`UTF-8`编码
解释:
UTF-8 编码具有更广泛的适应性,BOM 在使用程序或工具处理文件时可能造成不必要的干扰

#### [强制]引入 `CSS` 时必须指明 `rel="stylesheet"`
示例:
```
<link rel="stylesheet" href="demo.css">
```

#### [建议]引入 `CSS` 和 `JavaScript` 时无须指明 `type` 属性
解释:
`text/css` 和 `text/javascript` 是 type 的默认值。

#### [建议]在 `head` 中引入页面需要的所有 `CSS` 资源，`JavaScript` 应当放在页面末尾，或采用异步加载
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

#### 
