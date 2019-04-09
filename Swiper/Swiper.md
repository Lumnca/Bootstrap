# :star:Swiper教程 #

:arrow_double_down:[Swiper使用](#a1)


<b id="a1"></b>

### :ticket:1.Swiper使用 ###

首先加载插件，需要用到的文件有swiper.min.js和swiper.min.css文件。可下载[Swiper](https://www.swiper.com.cn/download/index.html#file1)文件或使用[CDN](https://www.swiper.com.cn/cdn/index.html)。

我们这里使用在线的CDN,下面就可以运行和展示一个轮播图

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8"> 
    <title>Swiper教程</title>
    <link rel="stylesheet" href="css/bootstrap.css">
    <script src="js/bootstrap.js"></script>
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
        pre{
            color: #6699ff;
            border: 3px double #9b59b6;
            font-weight: 500;
            font-size: 25px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        h2{
            color: #a03f8b;
        }
        p{
            font-weight: 500;
            font-size: 19px;
        }
    </style>
</head>
<body>
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide" style="background: #5bad87;">欢迎使用Swiper</div>
            <div class="swiper-slide" style="background: #1d7d8a;">分页轮播神器</div>
            <div class="swiper-slide" style="background: #a03f8b;">自制教程</div>
        </div>
    </div>
</body>
<script>
var mySwiper = new Swiper ('.swiper-container', {
    autoplay : true
  }) 
</script>
</html>
```

如上代码，首先需要添加分页轮播标签:

```html
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide" style="background: #5bad87;">欢迎使用Swiper</div>
            <div class="swiper-slide" style="background: #1d7d8a;">分页轮播神器</div>
            <div class="swiper-slide" style="background: #a03f8b;">自制教程</div>
        </div>
    </div>
```

外层div的class名可以自定义，但是内部class名称不能改变。如上首先声明一个实现的区域即：swiper-container，可自行定义名称，然后再声明swiper-wrapper类代表着在这个区域中切换以及分页，最后就是切换选项：swiper-slide类。完成后，需要初始化这个实现的区域，即外层div：

```javascript
var mySwiper = new Swiper ('.swiper-container', {
    autoplay : true
  }) 
```

Swiper采用构造方法形式声明，第一个参数为外层div的类名，需要加上'.',第二个参数是配置项。我们这里只包含了一个属性值 autoplay 这是一个自动切换的轮播图。

[实体样式](index.html)



