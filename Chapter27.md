# Chapter27 使用Window对象
### 1.获取Window对象
两种方法：<br>
1. window.窗口属性
2. document.defaultView.窗口属性
```
<!DOCTYPE html>

<html>
<head>
    <title>Chapter27</title>
</head>

<body id="bod">
    <table>
        <tr>
            <th>outerWidth:</th><td id="owidth"></td>
        </tr>
        <tr>
            <th>outerHeight:</th><td id="oheight"></td>
        </tr>
    </table>
    
    <script type="text/javascript">
        document.getElementById("owidth").innerHTML=window.outerWidth;
            //使用全局变量window来获取window对象
        document.getElementById("oheight").innerHTML=document.defaultView.outerHeight;
            //使用在Document对象上加defaultView属性
            
            //这里用以上两种方式，用Window对象来读取outerWidth和outerHeight属性值
    </script>
</body>
</html>

```

### 2.获取窗口信息
```
<!DOCTYPE html>

<html>
<head>
    <title>Chapter27</title>
    <style>
        table{
            border-collapse:collapse;
            border:thin solid black;
        }
    </style>
</head>

<body>
    <table border="1">
        <tr>
            <th>outerWidth:</th><td id="ow"></td>
            <th>outerHeight:</th><td id="oh"></td>
        </tr>
        <tr>
            <th>innerWidth:</th><td id="iw"></td>
            <th>innerHeight:</th><td id="ih"></td>
        </tr>
        <tr>
            <th>screen.width:</th><td id="sw"></td>
            <th>screen.height:</th><td id="sh"></td>
        </tr>
    </table>
    
    
    <script type="text/javascript">
        document.getElementById("ow").innerHTML=window.outerWidth;//获取窗口高度，包括边框和菜单栏等
        document.getElementById("oh").innerHTML=window.outerHeight;//获取窗口宽度，包括边框和菜单栏等
        document.getElementById("iw").innerHTML=window.innerWidth;//获取窗口内容区域高度
        document.getElementById("ih").innerHTML=window.innerHeight;//获取窗口内容区域宽度
        document.getElementById("sw").innerHTML=window.screen.width;//返回一个描述屏幕的Screen对象
        document.getElementById("sh").innerHTML=window.screen.height;
    </script>
</body>
</html>
```

### 3.与窗口进行交互
window对象有提供一组方法，可以用它们与包含文档的窗口进行交互
```
<!DOCTYPE html>

<html>
<head>
    <title>Chapter27</title>
</head>

<body>
    <p>
        <button id="scroll">Scroll</button>
        <button id="print">Print</button>
        <button id="close">Close</button>
    </p>
    <p>
        There are lots of different kinds of fruit.
        adafd da fadg qg qga.
        adfadf  AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA.
        AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
        
        aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa.
        aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaabbbbbbbbbbbbbbbbbbb.
        cccccccccccccccccccccccccccccccccccccccccccccccccccccc.
        aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa.
        aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa.
        sxxxxxxxxxxxxxxxfajaalllllllllllllllllllllllllllllllllllllll.
        aaaaaaaaaaaaaaaaoooooooooooooooooooooooooooooooooooooooooooo.
        kkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkkk.
    </p>
    <script>
        var buttons=document.getElementsByTagName("button");
        for(var i=0;i<buttons.length;i++)
        {
            buttons[i].onclick=handleButtonPress;
        }
        
        function handleButtonPress(e)
        {
            if (e.target.id=="print")
            {
                window.print();//提示用户打印页面
            }
            else if (e.target.id=="close")
            {
                window.close();//关闭窗口
            }
            else
            {
                window.scrollTo(400,400);//让文档滚动到指定位置
            }
        }
    </script>
</body>
</html>
```
