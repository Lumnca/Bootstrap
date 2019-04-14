# :star:Pagination配置项 #

Pagination是分页的配置项，也就是对显示每个分页的标记的配置，其参数配置如下目录：


:arrow_double_down:[el配置项](#a1)

:arrow_double_down:[type配置项](#a2)

:arrow_double_down:[progressbarOpposite配置项](#a3)

:arrow_double_down:[dynamicBullets配置项](#4)

:arrow_double_down:[hideOnClick配置项](#5)

:arrow_double_down:[clickable配置项](#6)

:arrow_double_down:[方法组](#？)



<b id="a1"></b>

### :ticket:1.el配置项 ###

该配置选项是显示分页标志，即我们常见的分页圆点显示，如下：

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8"> 
    <title>Pagination配置参数</title>

    <link  rel="icon" href="../img/windows.png">

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/css/swiper.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/css/swiper.min.css">   
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/js/swiper.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/js/swiper.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/js/swiper.esm.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/js/swiper.esm.bundle.js"></script>
    <style>
        .swiper-slide{
            display: flex;
            justify-content: center;
            align-items: center;
            height: 200px;
            font-size: 32px;
            font-weight: 700;
            color: aliceblue;
        }
        h2{
            color: #a03f8b;
        }
        p{
            font-weight: 500;
            font-size: 19px;
        }
        .swiper-container{
            height: 400px;
            border: 2px solid rgb(92, 163, 245);
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide" style="background: #5bad87;height:300px;">转换样式slide</div>
            <div class="swiper-slide" style="background: #1d7d8a;height:300px;">转换样式slide</div>
            <div class="swiper-slide" style="background: #a03f8b;height:300px;">转换样式slide</div>
        </div>
        <div class="swiper-pagination"></div> 
    </div>

</body>
<script>
var mySwiper = new Swiper('.swiper-container',{
    pagination: {
        el: '.swiper-pagination',
    }
})
</script>
</html>
```

相比以前的我们这里标签多了`<div class="swiper-pagination"></div> `这个标签内容，该div用于显示分页的位置，如果在分页里面则只能在对应的页面显示，所以最好放在所有页面的外面，区块的里面，这样就可以居中排布。当然还可以自动播放来自动显示求换分页标志：

```javascript
var mySwiper = new Swiper('.swiper-container',{
    autoplay : true,
    pagination: {
        el: '.swiper-pagination',
    }
})
```

[运行示例](Pagination/pagination.html)

<b id="a2"></b>

### :ticket:2.type配置项 ###

type配置分页的样式， 分页器样式类型，type参数可选

* bullets  圆点（默认）
* fraction  分式 
* progressbar  进度条
* custom 自定义

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8"> 
    <title>Pagination配置参数</title>

    <link  rel="icon" href="../img/windows.png">

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/css/swiper.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/css/swiper.min.css">   
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/js/swiper.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/js/swiper.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/js/swiper.esm.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.2/js/swiper.esm.bundle.js"></script>
    <style>
        .swiper-slide{
            display: flex;
            justify-content: center;
            align-items: center;
            height: 200px;
            font-size: 32px;
            font-weight: 700;
            color: aliceblue;
        }
        h2{
            color: #a03f8b;
        }
        p{
            font-weight: 500;
            font-size: 19px;
        }
        .swiper-container,.swiper-container1{
            height: 400px;
            border: 2px solid rgb(92, 163, 245);
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide" style="background: #5bad87;height:300px;">转换样式slide</div>
            <div class="swiper-slide" style="background: #1d7d8a;height:300px;">转换样式slide</div>
            <div class="swiper-slide" style="background: #a03f8b;height:300px;">转换样式slide</div>
        </div>
        <div class="swiper-pagination"></div> 
    </div>
</body>
<script>
var mySwiper = new Swiper('.swiper-container',{
    autoplay : true,
    pagination: {
        el: '.swiper-pagination',
        type : 'progressbar'
        /*
        bullets’  圆点（默认）
        ‘fraction’  分式 
        ‘progressbar’  进度条
        ‘custom’ 自定义
        */
    }
})
</script>
</html>
```

运行可以看到实例，不建议一个页面多个轮播图，会导致排布错乱。

[运行示例](Pagination/pagination.html)

<b id="a3"></b>

### :ticket:3.progressbarOpposite配置项 ###

在type配置为 type : 'progressbar'是水平的进度条，可以使用该配置使得方向为垂直：

```javascript
var mySwiper = new Swiper('#one',{
    autoplay : true,
    pagination: {
        el: '#pone',
        type : 'progressbar',
        progressbarOpposite : true,
        
    },
})
```

其默认值为false，参数为true即可开启，注意版本！

<b id="a4"></b>

### :ticket:4.dynamicBullets配置项 ###

dynamicBullets配置项开启小圆点缩小渐变。默认为false，开启为true，用于圆点样式。

```javascript
var mySwiper = new Swiper('#two',{
    autoplay : true,
    pagination: {
        el: '#ptwo',
        dynamicBullets : true
    },
})
```

<b id="a5"></b>

### :ticket:5.hideOnClick配置项 ###

默认分页器会一直显示。这个选项设置为true时点击Swiper会隐藏/显示分页器。即点击轮播图会隐藏起来，再次点击会显示。默认值为false

```javascript
var mySwiper = new Swiper('#two',{
    autoplay : true,
    pagination: {
        el: '#ptwo',
        dynamicBullets : true,
        hideOnClick : true
    },
})
```

<b id="a6"></b>

### :ticket:6.clickable配置项配置项 ###

该配置项用于点击分页标记时可以切换页面,只适用于圆点：

```javascript
var mySwiper = new Swiper('#two',{
    pagination: {
        el: '#ptwo',
        dynamicBullets : true,
        hideOnClick : true,
        clickable : true
    },
})
```

默认为false，代表没有按钮切换功能，配置为true开启。运行后点击分页圆点即可看到效果。

<b id="a？"></b>

### :ticket:方法组 ###

**renderBullet方法**

渲染分页器小点。这个参数允许完全自定义分页器的指示点。接受指示点索引和指示点类名作为参数。如下例子：

```javascript
    <style>
        .swiper-slide{
            display: flex;
            justify-content: center;
            align-items: center;
            height: 200px;
            font-size: 32px;
            font-weight: 700;
            color: aliceblue;
        }
        h2{
            color: #a03f8b;
        }
        p{
            font-weight: 500;
            font-size: 19px;
        }
        .swiper-container{
            border: 2px solid rgb(92, 163, 245);
            border-radius: 5px;
        }
        .swiper{
            border: 1px solid;
            border-radius: 50%;
            background: rgb(146, 110, 110);

        }
    </style>
</head>
<body>
    <div class="swiper-container" id="one">
        <div class="swiper-wrapper">
            <div class="swiper-slide" style="background: #5bad87;height:300px;">转换样式slide</div>
            <div class="swiper-slide" style="background: #1d7d8a;height:300px;">转换样式slide</div>
            <div class="swiper-slide" style="background: #a03f8b;height:300px;">转换样式slide</div>
        </div>      
        <span class="swiper-pagination" id="pone"></span> 
    </div>
</body>
<script>
var mySwiper = new Swiper('#one',{
    autoplay : true,
    pagination: {
        el: '#pone',
        clickable: true,
        renderBullet: function (index, className) {
          return '<span class="' + className + '">' +"<span class='swiper'>"+ (index + 1) +"</span>" +'</span>';
        },
    },
})
</script>
```

如上renderBullet方法含有两个参数，返回值是取代原有样式的值，index是分页的圆点索引，className是原有绑定圆点标签的样式，即上面的swiper-pagination样式值，如果不添加其他样式则会显示重复覆盖。swiper样式为自己写的圆点样式。

[运行示例](Pagination/render.html)





