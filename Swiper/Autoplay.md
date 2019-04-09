# :star:Autoplay配置项 #

:arrow_double_down:[Autoplay配置项](#a1)

:arrow_double_down:[Autoplay控制函数](#a2)


<b id="a1"></b>

### :ticket:1.Autoplay配置项 ###

Autoplay是自动执行的配置项，其默认是关闭的，如果需要启用该配置，需要将其设置为true：

```javascript
var mySwiper = new Swiper ('.类名', {
    autoplay : true
}) 
```

设置后里面的值全部采用默认值：

```javascript
var mySwiper = new Swiper('.swiper-container', {
  autoplay:true,//等同于以下设置
  /*autoplay: {
    delay: 3000,
    stopOnLastSlide: false,
    disableOnInteraction: true,
    },*/
});
</scr
```

可以看出延迟为3s，其中还包含了其他属性，下面一一介绍。

**delay ：** 延时时间，单位毫秒ms. 如`delay: 3000`代表3秒切换。

如设置为1s执行一次

```javascript
var mySwiper = new Swiper('.swiper-container', {
  autoplay: {
    delay: 2000,//2秒切换一次
  },
});
```

**stopOnLastSlide：** 当切换到最后一个slide时停止自动切换。（loop模式下无效）。属性值为bool类型即true,false。为true时切换到最后一个停止继续切换。false不停止即循环。默认值为false。

```javascript
  var mySwiper4 = new Swiper ('.swiper-container4', {
    autoplay : {
        delay : 2000,
        stopOnLastSlide :true
    }
  }) 
```

**disableOnInteraction：** 用户操作swiper之后，是否禁止autoplay。默认为true：停止。如果设置为false，用户操作swiper之后自动切换不会停止，每次都会重新启动autoplay。操作包括触碰，拖动，点击pagination等。
需要借助其他配置项。

**reverseDirection：** 反向自动轮播，bool类型默认为false。

```javascript
var mySwiper = new Swiper('.swiper-container',{
  autoplay: {
    reverseDirection: true,
  },
})
```


**waitForTransition:** 等待过渡完毕。自动切换会在slide过渡完毕后才开始计时。虚拟位移状态下自动切换（virtualTranslate）可能需要关闭此选项。bool类型，默认为true。

```javascript
  var mySwiper = new Swiper('.swiper-container',{
    speed:2500,
    autoplay: {
      delay: 2000,
      waitForTransition: false,
    },
  })
```

值得说明的是如果想得到过渡实例，需要添加一个过渡的速度值：`speed:2500` 代表过渡过程为2.5s也是切换的速度，又`delay: 2000`说明过渡完成后2s后继续过渡下一界面。就表示如果不是过渡完毕再等待切换就使用false值，如果需要等待过渡完毕后，再等待切换时间就用true。

<b id="a2"></b>

### :ticket:2.Autoplay控制函数 ###

**mySwiper.autoplay.running参数**

>如果Swiper开启了autoplay，这个值为true。

我们可以使用该方法来判断是否自动播放：

```javascript
var mySwiper = new Swiper('.swiper-container',{
  autoplay:true,
})

if(mySwiper.autoplay.running){
    console.log("已开启自动播放");
}
else{
    console.log("未开启自动播放");
}
```

如上会在控制台输出"已开启自动播放"

**mySwiper.autoplay.start()函数**

该函数用于启动自动播放切换。

**mySwiper.autoplay.stop()函数**

该函数用于关闭自动播放切换。

这两种函数与第一个参数配合使用可以控制切换。下面是一个点击按钮在停止与播放的按钮。下面是处理的js代码

```javascript
var mySwiper6 = new Swiper ('.swiper-container6', {
      speed : 5000,
    autoplay : {
        delay : 1000,
        waitForTransition : false
    }
  }); 
function stop(){
    mySwiper6.autoplay.stop();
}
function start(){
    mySwiper6.autoplay.start();
}
```

标签内容：

```html
    <div class="swiper-container6">
            <div class="swiper-wrapper">
                <div class="swiper-slide" style="background: #5bad87;"> disableOnInteraction : false<br>过渡界面1</div>
                <div class="swiper-slide" style="background: #1d7d8a;">过渡界面2</div>
                <div class="swiper-slide" style="background: #a03f8b;">过渡界面3</div>
            </div>
    </div>
    <div class="container">
        <br>
        <button onclick="stop()" class="btn btn-primary">停止状态</button>
        <button onclick="start()" class="btn btn-primary">开启状态</button>
    </div>
```

点击按钮就可以改变状态，由于是过渡动画，需要在过渡完成才能停止。

[实体样式](Autoplay.html)