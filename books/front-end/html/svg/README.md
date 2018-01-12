## svg
#### svg嵌套svg 子svg设置的起始点默认向下平移10 向右平移10
* __`viewBox`__ 允许指定一个给定的一组图像伸展以适应特定的容器元素
## rect
* __`rx ry`__ 圆角边框
## path
### 一个大写的命令指明他的参数是绝对位置，而小写的指令指明相对于当前位置的点(上一个字母的最后一个点)
### __`d`__ 包含一系列路径描述
#### 贝塞尔曲线
* __`三次贝塞尔曲线`__ 需要控制点 (20, 20)(40, 20) 终点(50, 10) 加S(只需要一个控制点 终点) 添加一个三次贝塞尔曲线 与前一个等比放大
```html
    <path d="M10 10 C 40 10, 65 10, 95 80" stroke="black" fill="transparent"/>
    <path d="M10 80 C 40 10, 65 10, 95 80 S 150 150, 180 80" stroke="black" fill="transparent"/>
```
* __`二次贝塞尔曲线`__  需要控制点一个控制点 一个终点 加T(终点) 添加一个二次贝塞尔曲线 与前一个等比放大
```html
    <path d="M20,230 Q40,205 50,230" fill="none" stroke="blue" stroke-width="5"></path>
    <path d="M20,230 Q40,205 50,230 T90,230" fill="none" stroke="blue" stroke-width="5"></path>
```
#### 弧形命令A rx ry x-axis-rotation large-arc-flag sweep-flag x y
* __`rx`__ x轴半径
* __`ry`__ y轴半径
* __`x-axis-rotation`__ 弧形的旋转情况
* __`large-arc-flag`__ 弧线是大于还是小于180度
  * __`0`__ 小角度弧
  * __`1`__ 大角度弧
* __`sweep-flag`__ 弧线方向
  * __`0`__ 从起点到终点沿逆时针画弧
  * __`1`__ 从起点到终点沿顺时针画弧
* __`x y`__  两个参数是指定弧形的终点
#### 关闭路径Z
## g
* 用来将SVG中的元素进行分组操作，分组后可以看成一个单独的形状，统一进行转换，同时g元素的样式可以被子元素继承，但是它没有X,Y属性，不过可以通过transform来移动它；
## def
* 用于定义在SVG中可重用的元素，def元素不会直接展示出来，可以通过use元素来引用；
## use
* 通过它来复用def元素，也包括<g>、<symbol>元素，使用<use xlink: href="#id"/>即可调用；
## stroke
* __`stroke-dasharray`__ 用于使用虚线呈现SVG形状的描边，需要提供一个数值数组来描述
```html
    <div class="percent">
        <svg class="svg" width="44" height="44">
            <circle cx="22" cy="22" r="17" stroke-width="5" stroke="#D1D3D7" fill="none"></circle>
            <circle class="circle" cx="22" cy="22" r="17" stroke-width="5" stroke="#00A5E0" fill="none" transform="matrix(0,-1,1,0,0,44)" stroke-dasharray="10 106"></circle>
        </svg>
        <span class="percent-number" title="">' + rate + '</span>
    </div>
```
## 动画 [参考文章](article)
```html
<svg width="800" height="250" version="1.1" xmlns="http://www.w3.org/2000/svg">
    <!--set间隔3s向下走到cy为160地点-->
    <circle cx="80" cy="50" r="40" stroke="green" fill="#C3413D" stroke-width="5">
        <set attributeName="cy" attributeType="XML" to="160" begin="3s"></set>
    </circle><--animate设置动画并循环-->
    <circle cx="200" cy="50" r="40" stroke="#FFC302" fill="#635147" stroke-width="5">
        <animate attributeName="cy" from="160" to="60" begin="0s" dur="2s"></animate>
    </circle><--animateTransform设置放大1.6倍并循环-->
    <circle cx="320" cy="50" r="40" stroke="#C3413D" fill="#FFF2C8" stroke-width="5">
        <animateTransform attributeName="transform" begin="0s" dur="3s" type="scale" from="1" to="1.6" repeatCount="3"></animateTransform>
    </circle>

  <!--animateMotion设置路径动画-->
  <g transform="translate(500,60)">
    <path d="M10,110 A120,120 -45 0,1 110 10 A120,120 -45 0,1 10,110" stroke="#9B7B56" stroke-width="2" fill="none" id="theMotionPath" ></path>
    <circle  r="5" fill="#FFC302">
        <animateMotion dur="6s" repeatCount="indefinite">
            <mpath xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#theMotionPath"></mpath>
        </animateMotion>
    </circle>
  </g>
</svg>
```

[article]:https://zhuanlan.zhihu.com/p/25016633 "svg文章"
