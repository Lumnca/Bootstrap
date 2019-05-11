# :star:Navigation配置项 #

Navigation是显示前后页的按钮的配置项，其主要为以下：

**navigation** : 声明按钮，如下

```html
 <div class="swiper-container" id="p1">
        <div class="swiper-wrapper">
            <div class="swiper-slide" style="background:#a03f8b">Slide 1</div>
            <div class="swiper-slide" style="background:#7b77b8">Slide 2</div>
            <div class="swiper-slide" style="background:#219c88">Slide 3</div>
        </div>
        <div class="swiper-button-prev" id="a1"></div><!--左箭头-->
        <div class="swiper-button-next" id="b1"></div><!--右箭头-->
    </div>
```

js代码：

```javascript
var mySwiper = new Swiper('#p1', {
        navigation: {
          prevEl: '#a1'  ,//绑定左箭头
          nextEl: '#b1'   //绑定右箭头
        },
      });
```

其中  prevEl代表前一页， nextEl代表后一页。

**hideOnclick** ： 点击页面是否隐藏按钮，默认为false，不会隐藏按钮。

只需要添加该属性即可

```javascript
var mySwiper2 = new Swiper('#p2', {
        navigation: {
          prevEl: '#a2',  //绑定左箭头
          nextEl: '#b2',  //绑定右箭头
          hideOnClick: true //点击界面隐藏按钮
        },
      });
```

**disabledClass ： className**: 当按钮不能点击时的触发的类名

**hiddenClass ： className**: 按钮隐藏时触发的类名

```javascript
      var mySwiper3 = new Swiper('#p3', {
        navigation: {
          prevEl: '#a3'  ,//绑定左箭头
          nextEl: '#b3'  ,//绑定右箭头
          hideOnClick : true,
          disabledClass: 'my-button-disabled',  //当按钮不能点击时的触发的类名
          hiddenClass: 'my-button-hidden', //按钮隐藏时触发的类名
        },
      });
```

对应触发的css类

```css
        .my-button-hidden{
            background: #000;
        }
        .my-swiper-button{
            background-image: url("../img/windows.png")
        }

```

### 按钮样式dom与方法 ###

navigation.$nextEl 后按钮DOM

navigation.$prevEl 前按钮DOM

navigationHide按钮隐藏触发函数

navigationShow按钮显示触发函数

函数在on属性中声明执行。
