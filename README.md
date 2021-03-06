# Gansu-University-Painted-Pottery-Network

中文名:  <a href="javascript:void(0)">甘肃大学生彩陶网</a>

>
>
><a href="https://lovobin.github.io/Gansu-University-Painted-Pottery-Network/index.html">https://lovobin.github.io/Gansu-University-Painted-Pottery-Network/ </a>  （布局展示）

+ 尺寸标注图

  
  
  ![尺寸标注图](https://img-blog.csdnimg.cn/20201124122625573.png)

>  `ICO在线制作推荐:` https://tool.lu/favicon/
>
> ​	使用方法:  
>
> + 上传图片，剪裁
> + 点击下载,跳转后右鼠标另存为 `*.ico`文件



###  2020年-11月-18日:

> 
>
> 完成 Header-logo Nav
>
> 背景颜色改动
>
> 图片改动
>
> 文本信息改动
>
> 

![完成 Header-logo Nav](https://img-blog.csdnimg.cn/20201119015723538.gif#pic_center)



###  2020年-11月-19日；

> ```
> 应用: Animation
> 
> 布局: Flex
> 
> ```

```css
图片相对垂直居中:
    position: absolute;
    left: 50%;
    transform: translate(-50%);
```

+ 整体效果预览

  ![布局无坍塌](access/gif/2020-11-19.gif)



###  2020年11月-20日:

+ 修复搜索框显示问题

  ![最终使用](https://gitee.com/wang_hong_bin/pic-go-photos/raw/master/searchBtn.png)

+ 修复`card`背景颜色显示

  + 采用`float`布局

  + 添加`css3 animation`

  + 使用linear-gradient

    + ` linear-gradient()`推荐:

      
      
      > 渐变颜色获取:
      >
      > 
      >
      > <a href="https://webgradients.com/">https: //webgradients.com/</a>
      >
      > 
      >
      > <a href="https://gradient.shapefactory.co/">https: //gradient.shapefactory.co/</a>
      >
      > 
    
    + 原图:
    
      ![背景色未修复前](https://gitee.com/wang_hong_bin/pic-go-photos/raw/master/fixCard.png)
    
    + 修复后(维护中······)

+ 准备轮播图实现

  + 存在一条 `bug`

    + `bug`描述:  在判断了最后一张图片的情况下,`next`事件依然显示一张空白背景(已解决稍微有点缺陷,在提升后修复)
    
    + `js`
    
      ```javascript
      console.log("正在加载 Slider.js·········");
      
      const sliders = document.querySelectorAll(".slider");
      const prev = document.querySelector("#prev");
      const next = document.querySelector("#next");
      
      const nextSlider = function () {
          // get current class
          const current = document.querySelector(".current");
          if (current.nextElementSibling) {
              // add current to next sibling
              current.nextElementSibling.classList.add("current");
          } else {
              // add current to start
              sliders[0].classList.add("current");
          }
          // clear current
          setTimeout(() => current.classList.remove("current"));
      };
      
      const prevSlider = function () {
          // get current class
          const current = document.querySelector(".current");
          if (current.previousElementSibling) {
              // add current to next sibling
              current.previousElementSibling.classList.add("current");
          } else {
              // add current to start
              sliders[sliders.length - 1].classList.add("current");
          }
          // clear current
          setTimeout(() => current.classList.remove("current"));
      };
      
      // click Event
      next.addEventListener("click", function () {
          nextSlider();
      });
      prev.addEventListener("click", function () {
          prevSlider();
      });
      
      // 定时器
      var timer = setInterval(function () {
          nextSlider();
      }, 5000);
      
      // 鼠标移入移除
      var rmTimer = document.querySelector("#Slider ");
      rmTimer.addEventListener("mouseenter", function () {
          // 鼠标移入清除 定时器
          clearInterval(timer);
          // 清除定时器变量
          timer = null;
          console.log("鼠标移入,清除定时器···");
      });
      rmTimer.addEventListener("mouseleave", function () {
          // 鼠标移出开启定时器
          timer = setInterval(function () {
              nextSlider();
          }, 2000);
          console.log("鼠标移入,开启定时器···");
      });
      ```
    
      

+ 添加新布局

  + 考虑瀑布流(放弃选择)
  + 添加`footer`页脚,已完成 !

+ 暂时完成首页布局



> 
>
> 疑问: `float 中`未使用 清除浮动，什么时候使用清除浮动(····)
>
> 



###  2020年11月21日:

+ 添加第一个子页

  + 子页新布局考虑

  + 整体颜色更改

  + 动画内容更改

  + 添加 `JS`事件

  + 添加时间倒计时布局(考虑中····)

  + `H5`新标签的使用

    ```html
    <figure>  </figure>
    
    	figure:
    
    <figcaption> </figcaption>
    
    	figcaption:
    ```

+ `css3 :hover`理解与掌握使用

  + `css2`选择器

    ```html
    element1 + element2 选择器匹配出现在 element 后面的临近的 element2
    ```

  + `css3`选择器

    ```html
    element1 ~ element2 选择器匹配出现在 element1 后面的 element2
    ```

+ `box-shadow`理解使用

  ```scss
  box-shadow: offset-x offset-y blur spread color position;
  ```

+ 翘边阴影的使用

  ```scss
  transform: skew(角度); // skew() 扭曲
  ```

+ `linear-gradient()`

  ```scss
  background: linear-gradient();
  ```

+ 添加新属性`filter`的使用

  ```scss
  filter: sepia(.2) brightness(1) contrast(1.3);
  
  sepia: 将图像转换为深褐色。值定义转换的比例。值为100%则完全是深褐色的，值为0%图像无变化。值在0%到100%之间，则是效果的线性乘子。若未设	
  		置，值默认是0。
  
  brightness: 给图片应用一种线性乘法，使其看起来更亮或更暗。如果值是0%，图像会全黑。值是100%，则图像无变化。其他的值对应线性乘数效果。值超
  
  			过100%也是可以的，图像会比原来更亮。如果没有设定值，默认是1。
  
  contrast: 调整图像的对比度。值是0%的话，图像会全黑。值是100%，图像不变。值可以超过100%，意味着会运用更低的对比。若没有设置值，默认是1。
  ```

+ 首页局部锚链接添加

  ```HTML
  <!-- 
      彩陶文化: Painted pottery culture
      
      ID简称: ppc
  -->
  ```

  + 学术展览(`id: A-e`)
  + 彩陶文化(`id: ppc`)
  + 联系我们(`id: email`)

+ 添加返回顶部与返回首页功能

+ `GoTop`

  ![当经过某一元素高度时显示该元素](https://gitee.com/wang_hong_bin/pic-go-photos/raw/master/gotop.png)
  
  + 鼠标滚轮事件
  
    ```javascript
    
    // 获取返回顶部按钮
    var gotop = document.querySelector('.gotop');
    // 获取 cardShow 的偏移量
    var cardShow = document.querySelector('#cardShow');
    // 当 cardShow 出现时,返回顶部按钮显示
    var cardShowTop = cardShow.offsetTop;
    document.addEventListener('scroll', function () {
        if (window.pageYOffset >= cardShowTop) {
            gotop.style.opacity = 1;
            gotop.style.transition = "all .5s ease-in-out";
        } else {
            gotop.style.opacity = 0;
        }
    });
    
    // 获取返回顶部 gotop 按钮点击事件
    gotop.addEventListener('click', function () {
        // window.scroll(0, 0); 无动画状态
        /*
         * 添加动画函数:
         *  obj： window
         *  target: 返回顶部(0)
         *  callback 暂时不需要
         * */
        animation(window, 0);
    });
    
    ```
  
  + 动画函数封装
  
    ```javascript
    
    // 封装动画函数
    function animation(obj, target, callback) {
        /*
        * object: 目标对象
        * target: 目标位置
        * */
        clearInterval(obj.timer)
        obj.timer = setInterval(function () {
            var step = (target - window.pageYOffset) / 10;
            step = step > 0 ? Math.ceil(step) : Math.floor(step);
            if (window.pageYOffset == target) {
                // 停止动画 即: 停止定时器
                clearInterval(obj.timer);
                callback && callback();
            }
            //  水平移动 obj.style.left = window.pageYOffset + step + 'px';
            window.scroll(0, window.pageYOffset + step);
        }, 15)
    }
    ```
  
    
  
  

###  2020年11月22日:

+ 添加第二个子页

+ `box-shadow`

+ `text-shadow`
+ `<marquee> </marquee>`

###  2020年11月23日:

+ `background: linear-gradient();`

+ `定位`

+ 效果图

  ![2020年11月23日:](https://gitee.com/wang_hong_bin/pic-go-photos/raw/master/day03.png)

###   2020年11月24日:

![图片展览布局](https://gitee.com/wang_hong_bin/pic-go-photos/raw/master/day04.png)