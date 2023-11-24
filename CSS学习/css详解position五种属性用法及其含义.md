# css详解position五种属性用法及其含义

position（定位）
position — 作为css属性三巨头（position、display、float）之一，它的作用是用来决定元素在文档中的定位方式。其属性值有五种，分别是 — static（正常定位）、relative（相对定位）、absolute（绝对定位）、fixed（固定定位）、sticky（粘性定位）。

## static（正常定位）
static(正常定位) 是元素position属性的默认值，包含此属性的元素遵循常规流1。

正常定位呈现常规流的示例html代码：
```
<!DOCTYPE html>
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>正常定位呈现常规流的示例</title>
        <style type="text/css">
            * {
                margin: 12px;
                background-color: white;
            }

            .block {
                background-color: #f00;
            }
    
            .inline {
                display: inline;
                background-color: #ff0;
            }
            
        </style>
    </head>
    <body>
        <div class="block">Fatman</div>
        <div class="block">Fatman</div>
        <div class="inline">Fatman</div>
        <div class="inline">Fatman</div>
        <div class="inline">Fatman</div>
        <div class="inline">Fatman</div>
    </body>
</html>
```

正常定位呈现常规流的示例效果图：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210410145034902.png)

当元素的position属性值为**static**时，元素的**top、right、bottom、left、z-index**属性都不会生效。

元素正常定位未添加top、right、bottom、left属性的示例html代码：
```
<!DOCTYPE html>
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>元素正常定位未添加top、right、bottom、left属性的示例</title>
        <style type="text/css">
            body {
                border: 1px solid black;
                padding: 12px;
            }
            
            div {
                width: 100px;
                height: 100px;
                background-color: #f00;
            }
        </style>
    </head>
    <body>
        <div></div>
    </body>
</html>
```
元素正常定位未添加top、right、bottom、left属性的示例效果图：
在这里插入图片描述

![1](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20104415.png?raw=true)

元素正常定位且添加top、right、bottom、left属性的示例html代码：
```
<!DOCTYPE html>
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>元素正常定位且添加top、right、bottom、left属性的示例</title>
        <style type="text/css">
            body {
                border: 1px solid black;
                padding: 12px;
            }
            
            div {
                top: 120px;
                right: 120px;
                bottom: 120px;
                left: 120px;
                width: 100px;
                height: 100px;
                background-color: #f00;
            }
        </style>
    </head>
    <body>
        <div></div>
    </body>
</html>
```
元素正常定位且添加top、right、bottom、left属性的示例效果图：

![2](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20104801.png?raw=true)

元素正常定位下，无论有无添加top、right、bottom、left属性，红色背景的div元素相对于body元素的边框都没有任何的位置变化，由此可以说明当元素的position属性值为static时，元素的top、right、bottom、left属性值不会生效。

正常定位的元素与相对定位的元素重叠的示例html代码：
```
<!DOCTYPE html>
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>正常定位的元素与相对定位的元素重叠的示例</title>
        <style type="text/css">
            body {
                border: 1px solid black;
                padding: 12px;
            }

            div {
                width: 100px;
                height: 100px;
            }

            #static {
                position: static;
                background-color: #f00;
                z-index: 999;
            }
            
            #relative {
                position: relative;
                top: -100px;
                left: 0;
                background-color: #ff0;
                z-index: 1;
            }
        </style>
    </head>
    <body>
        <div id="static"></div>
        <div id="relative"></div>
    </body>
</html>
```
正常定位的元素与相对定位的元素重叠的示例效果图：

![3](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20104912.png?raw=true)

ID为static的元素的z-index属性值明显高于ID为relative的元素。同理，在z轴，ID为static的元素应该比ID为relative的元素更靠近用户，事实上却是ID为relative的元素更靠近用户。

正常定位的元素与相对定位的元素重叠，但相对定位的元素的z-index值小于0时的示例html代码：
```
<!DOCTYPE html>
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>正常定位的元素与相对定位的元素重叠，但相对定位的元素的z-index值小于0时的示例</title>
        <style type="text/css">
            body {
                border: 1px solid black;
                padding: 12px;
            }

            div {
                width: 100px;
                height: 100px;
            }

            #static {
                position: static;
                background-color: #f00;
                z-index: 999;
            }
            
            #relative {
                position: relative;
                top: -100px;
                left: 0;
                background-color: #ff0;
                z-index: -1;
            }
        </style>
    </head>
    <body>
        <div id="static"></div>
        <div id="relative"></div>
    </body>
</html>
```
正常定位的元素与相对定位的元素重叠，但相对定位的元素的z-index值小于0时的示例效果图：

![4](D:\图片\Screenshots\屏幕截图 2023-11-24 105121.png)

将ID为relative的元素的z-index属性值修改负数后，在z轴ID为static的元素比ID为relative的元素更靠近用户,结合ID为relative的元素的z-index属性值为正数的情况，得出position属性值为static时，元素的z-index是不会受到设置值影响的2。


## relative（相对定位）
postion属性值为relative(相对定位) 的元素在不设置top、right、bottom、left这些属性时，其自身在文档中的定位效果与static并无区别，但加上top、right、bottom、left这些属性后，便会相对于自身在常规流中的位置进行定位。

在上文中阐述static时用到的ID为relative的元素用的就是相对定位，从其对应的效果图可以看出，虽然元素中含有值为-100px的top属性，将元素显示的位置相对于自身在常规流中的位置往上移动了100像素，但其自身在常规流中的位置仍然保留。

ID为relative的元素在常规流中的位置仍然保留的示例效果图：

![5](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20105013.png?raw=true)

相对定位的示例html代码：
```
<!DOCTYPE html>
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>相对定位的示例</title>
        <style type="text/css">
            body {
                border: 1px solid black;
                padding: 12px;
            }

            div {
                width: 100px;
                height: 100px;
                position: relative;
            }

            #div1 {
                background-color: red;
            }

            #div2 {
                background-color: black;
                top: 100px;
                left: 100px;
            }

            #div3 {
                background-color: gray;
            }
        </style>
    </head>
    <body>
        <div id="div1"></div>
        <div id="div2"></div>
        <div id="div3"></div>
    </body>
</html>
```
相对定位的示例效果图：

![6](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20105323.png?raw=true)

这里三个元素盒子都是用的相对定位：红色盒子因为没有设置top、right、bottom、left属性，其定位在自身在常规流中的位置；黑色盒子因为包含值均为100px的top和left两属性，所以其定位在相对于自身在常规流先靠下100像素，再靠右100像素的位置上；灰色盒子和红色盒子一样，没有设置top、right、bottom、left属性，但因黑色盒子在常规流中的位置仍然保留，所以灰色盒子所占位置并没有紧靠在红色盒子的下方，而是出现在距离红色盒子底部100像素的位置上。

## absolute（绝对定位）
absolute（绝对定位）与relative（相对定位）之间的区别是：relative（相对定位）并没有脱离文档流，而absolute（绝对定位）脱离了文档流；relative（相对定位）相对于自身在常规流中的位置进行偏移定位，而absolute（绝对定位）相对于离自身最近的定位祖先元素的位置进行偏移定位。

先解释何为脱离常规流，笔者将正常定位呈现常规流的示例html代码略作修改，得到：

绝对定位脱离常规流的示例html代码：
```
<!DOCTYPE html>
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>绝对定位脱离常规流的示例</title>
        <style type="text/css">
            * {
                margin: 12px;
                background-color: white;
            }
            
            .block {
                background-color: #f00;
            }

            .inline {
                display: inline;
                background-color: #ff0;
            }
            
        </style>
    </head>
    <body>
        <div class="block">Fatman</div>
        <div class="block" style="position: absolute;">Fatman</div>
        <div class="inline">Fatman</div>
        <div class="inline" style="position: absolute;">Fatman</div>
        <div class="inline">Fatman</div>
        <div class="inline">Fatman</div>
    </body>
</html>
```
绝对定位脱离常规流的示例效果图：

1[7](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20105451.png?raw=true)

从效果图中可以看出，添加了position属性值为absolute的块级元素并没有按预期独占一行，且同样添加了position属性值为absolute的行内元素也并没有按预期在每行中按从左至右的顺序依次排放元素。并且因为笔者没有给两个使用绝对定位的元素设置top、right、bottom、left属性，所以布局有种说不上来的诡异。

再说何为定位祖先元素：比如相对定位的元素中是相对于在常规流中的位置进行偏移定位，top、right、bottom、left属性的参考系是元素在常规流中的位置，而在绝对定位的元素中的参考系就是定位祖先元素。拥有相对定位属性值的祖先元素可以充当拥有绝对定位属性值的子孙元素的定位祖先元素。如果子孙元素没有定位祖先元素，会一直回溯到body元素，使用body元素充当自己的定位祖先元素。

相对定位元素充当绝对定位元素的定位祖先元素实现垂直水平居中的示例html代码：
```
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>相对定位元素充当绝对定位元素实现垂直水平居中的示例</title>
        <style type="text/css">
            body {
                border: 1px solid black;
                padding: 12px;
            }

            .parent {
                position: relative;
                width: 300px;
                height: 300px;
                background-color: #ff0;
            }

            .son {
                position: absolute;
                width: 100px;
                height: 100px;
                background-color: #f00;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
            }
        </style>
    </head>
    <body>
        <div class="parent">
            <div class="son"></div>
        </div>
    </body>
</html>
```
相对定位元素充当绝对定位元素的定位祖先元素实现垂直水平居中的示例效果图：


1[8](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20105553.png?raw=true)

红色盒子（绝对定位元素）在其定位祖先元素黄色盒子（相对定位元素）中垂直水平居中。

body充当绝对定位元素的定位祖先元素实现垂直水平居中的示例html：
```
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>body充当绝对定位元素实现垂直水平居中的示例</title>
        <style type="text/css">
            body {
                border: 1px solid black;
                padding: 12px;
            }

            .center {
                position: absolute;
                width: 100px;
                height: 100px;
                background-color: #f00;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
            }
        </style>
    </head>
    <body>
        <div class="center"></div>
    </body>
</html>
```
body充当绝对定位元素的定位祖先元素实现垂直水平居中的示例效果图：

![](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20105654.png?raw=true)

红色盒子（绝对定位元素）在其定位祖先元素body中垂直水平居中。


## fixed（固定定位）
fixed（固定定位）和absolute（绝对定位）很像，但也有两点不同：absolute（绝对定位）相对于定位祖先元素进行偏移定位，而fixed（固定定位）相对于窗口进行偏移定位；absolute（绝对定位）的定位祖先元素可以是相对定位的元素，而fixed（固定定位）的定位祖先元素只能是窗口。

固定定位实现垂直水平居中的示例html代码：
```
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>固定定位实现垂直水平居中的示例</title>
        <style type="text/css">
            body {
                border: 1px solid black;
                padding: 12px;
                height: 1000px;
            }

            .center {
                position: fixed;
                width: 100px;
                height: 100px;
                background-color: #f00;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
            }
        </style>
    </head>
    <body>
        <div class="center"></div>
    </body>
</html>
```
固定定位实现垂直水平居中的示例效果图：

![](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20105754.png?raw=true)

尽管上下滑动，却不会影响到红色盒子（固定定位元素）在视窗中垂直水平居中。

相对定位元素企图充当固定定位元素的定位祖先元素实现垂直水平居中的示例html代码：
```
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>相对定位元素企图充当固定定位元素的定位祖先元素实现垂直水平居中的示例</title>
        <style type="text/css">
            body {
                border: 1px solid black;
                padding: 12px;
            }

            .parent {
                position: relative;
                width: 300px;
                height: 300px;
                background-color: #ff0;
            }

            .son {
                position: fixed;
                width: 100px;
                height: 100px;
                background-color: #f00;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
            }
        </style>
    </head>
    <body>
        <div class="parent">
            <div class="son"></div>
        </div>
    </body>
</html>
```
相对定位元素企图充当固定定位元素的定位祖先元素实现垂直水平居中的示例效果图：

![](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20105911.png?raw=true)

相对定位元素并不能作为固定定位元素的参照物。


## sticky（粘性定位）
sticky（粘性定位）类似relative和fixed的结合，当元素设置position属性为sticky时，如果top、right、bottom、left四个属性都不设置具体值，sticky（粘性定位）不会生效，其表现效果与static一致3。
当在top、right、bottom、left四个属性中至少设置一个具体值时，元素具备两种状态 — 类似relative（相对定位状态）和类似fixed（固定定位状态）。以top:10px为例 ：当元素相对于窗口顶部的距离大于10px时，元素处于类似relative（相对定位状态），一旦元素相对于窗口顶部的距离小于或等于10px时，元素立马切换到类似fixed（固定定位状态）

粘性定位的示例html代码：
```
<!DOCTYPE html>
<html>
    <head>
        <meta name="charset" content="utf-8"/>
        <title>粘性定位的示例</title>
        <style type="text/css">
            body {
                border: 1px solid black;
                padding: 32px;
                margin: 32px;
                height: 1000px;
            }
            div {
                width: 100px;
                height: 100px;
                position: relative;
            }
            #div1 {
                background-color: red;
            }
            #div2 {
                background-color: black;
                position: sticky;
                top: 100px;
                left: 100px;
                padding: 0;
                margin: 0;
            }
            #div3 {
                background-color: gray;
            }
        </style>
    </head>
    <body>
        <div id="div1"></div>
        <div id="div2"></div>
        <div id="div3"></div>
    </body>
</html>
```
粘性定位的示例效果图：

![](https://github.com/know-ovo/Tesks/blob/main/CSS%E5%AD%A6%E4%B9%A0/image/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-11-24%20110016.png?raw=true)

在上下滚动视窗时，设置了粘性定位的黑色盒子会随着视窗一起滚动，直到触发条件top:100px，便“粘住”在距离窗口顶部100像素的位置上。

不过这里有两点需要注意：
1.当粘性定位的元素处于类似relative（相对定位状态）时，它并不是单纯的相对于自身在常规流中的位置进行的偏移定位；
2.当粘性定位的元素处于类似fixed（固定定位状态）时，它在常规流中的位置仍然保留。

关于第一点，当粘性定位的示例中黑色盒子的left属性值小于等于65像素（32px + 32px + 1px）时，黑色盒子都位于其在常规流的位置上，而当粘性定位的示例中黑色盒子的left属性值大于65像素（32px + 32px + 1px）时,黑色盒子将相对于其在常规流的位置的（left设定值减去65像素）进行定位。
关于第二点，当黑色盒子“粘住”时，红色盒子与灰色盒子之间的间隙并没有消除，由此得出黑色盒子在常规流中的位置仍然保留。




————————————————
版权声明：本文为CSDN博主「Fatman_」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_35508835/article/details/115573672

