## svg
* __`viewBox`__ 允许指定一个给定的一组图像伸展以适应特定的容器元素
## rect
* __`rx ry`__ 圆角边框
## path
#### 一个大写的命令指明他的参数是绝对位置，而小写的指令指明相对于当前位置的点(上一个字母的最后一个点)
* __`d`__ 包含一系列路径描述
## 贝塞尔曲线
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
