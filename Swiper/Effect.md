# :star:Effects配置项 #

Effects配置只要是设置切换的样式，其包含effect，fadeEffect,cubeEffect,coverflowEffect,filpEffect这5个配置项。


:arrow_double_down:[effect配置项](#a1)

:arrow_double_down:[fadeEffect配置项](#a2)

:arrow_double_down:[cubeEffect配置项](#a3)

:arrow_double_down:[coverflowEffect配置项](#a4)

:arrow_double_down:[filpEffect配置项](#a5)


<b id="a1"></b>

### :ticket:1.effect配置项 ###

effect为切换的样式，前面的样式默认为平滑，也就是平行移动。可以添加其他样式。如：

```javascript
var mySwiper = new Swiper ('.swiper-container1', {
    autoplay : true,
    //默认为slide,fade,cube,coverflow,filp
    effect : 'slide'
})
```

>其中slide为默认值，即平滑移动。其余是"fade"（淡入）"cube"（方块）"coverflow"（3d流）"flip"（3d翻转）。

<b id="a2"></b>

### :ticket:2.fadeEffect配置项 ###

fadeEffect配置项主要是用于配置样式为fade的设置，

可选参数：crossFade：

>默认：false。关闭淡出。过渡时，原slide透明度为1（不淡出），过渡中的slide透明度从0->1（淡入），其他slide透明度0。

>可选值：true。开启淡出。过渡时，原slide透明度从1->0（淡出），过渡中的slide透明度从0->1（淡入），其他slide透明度0。

>当你的slide中图片大小不同时可以用到。

```javascript
 var mySwiper = new Swiper ('.swiper-container1', {
    speed : 4500,
    autoplay : true,
    //默认为slide,fade,cube,coverflow,filp
    effect : 'fade',
    fadeEffect: {
        crossFade: true,
    }
})
```

添加一个过渡时间，你就可以看到淡入淡出的效果。

[运行示例](Effects/fadeEffect.html)

<b id="a3"></b>

### :ticket:3.cubeEffect配置项 ###


cubeEffect配置项用来配置样式为cube的样式，其包含以下4个参数：

* slideShadows：开启slide阴影。默认 true。
* shadow： 开启投影。默认 true。
* shadowOffset：投影距离。默认 20，单位px。
* shadowScale： 投影缩放比例。默认0.94。

如下配置：

```javascript
var mySwiper = new Swiper('.swiper-container1',{
    effect : 'cube',
    cubeEffect: {
        slideShadows: true,
        shadow: true,
        shadowOffset: 10,
        shadowScale: 0.88
    }
})
```

运行可以看到图片下面会有阴影，10代表与图片下端的距离，0.88是图片的宽度缩放。

[运行示例](Effects/cubeEffect.html)

<b id="a4"></b>

### :ticket:4.coverflowEffect配置项 ###

coverflowEffect用于配置3D翻转样式（coverflow），其包含以下参数：

* rotate：slide做3d旋转时Y轴的旋转角度。默认50。
* stretch：每个slide之间的拉伸值，越大slide靠得越紧。 默认0。
* depth：slide的位置深度。值越大z轴距离越远，看起来越小。 默认100。
* modifier：depth和rotate和stretch的倍率，相当于depth乘以modifier、乘以rotate乘以modifier、stretchmodifier，值越大这三个参数的效果越明显。默认1。
* slideShadows：开启slide阴影。默认 true。

如下配置：

```javascript
var mySwiper = new Swiper('.swiper-container',{
    speed : 3000,
    autoplay : true,
    effect : 'coverflow',
    coverflowEffect : {
        rotate : 90,
        stretch : 40,
        depth :10,
        modifier : 0.8,
        slideShadows : true
    }
})
```

[运行示例](Effects/coverflowEffect.html)


<b id="a5"></b>

### :ticket:5.filpEffect配置项 ###

filpEffect用于配置是否水平180度旋转，3d翻转有两个参数可设置。

* slideShadows：slides的阴影。默认true。
* limitRotation：限制最大旋转角度为180度，默认true。

```javascript
var mySwiper = new Swiper('.swiper-container1',{
    speed : 3000,
    autoplay : true,
  effect : 'flip',
  flipEffect: {
    slideShadows : true,
    limitRotation : true,
  }
})
```

[运行示例](Effects/coverflowEffect.html)