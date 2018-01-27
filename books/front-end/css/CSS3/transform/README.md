## transform
#### __`matrix(a, b, c, d, tx, ty)`__ 2D变换矩阵
* 平移矩阵 matrix(1, 0, 0, 1, tx, ty) x轴平移tx，y轴平移ty
* (中心)缩放矩阵 matrix(n, 0, 0, n, 0, 0) 缩放n倍
* (中心)旋转矩阵 matrix(cosθ, sinθ, -sinθ, cosθ, 0, 0) 旋转θ度 (逆时针旋转θ逐渐增大，顺时针旋转θ逐渐减小)
* 复核变换矩阵 图形中心缩放n倍，中心旋转θ度，平移tx, ty之后的矩阵 matrix(ncosθ, nsinθ, -nsinθ, ncosθ, tx, ty)

#### __`matrix3d(a1, b1, c1, d1, a2, b2, c2, d2, a3, b3, c3, d3, a4, b4, c4, d4)`__ 3D变换矩阵
* 平移矩阵 matrix(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, tx, ty, tz, 1) x轴平移tx，y轴平移ty，z轴平移tz
* (中心)缩放矩阵 matrix(n, 0, 0, 0, 0, n, 0, 0, 0, 0, n, 0, 0, 0, 0, 1) 缩放n倍
* 旋转矩阵
  * x轴 matrix(1, cosθ, sinθ, 0, 0, -sinθ, cosθ, 0, 0, 0, 0, 0, 0, 0, 0, 1) 旋转θ度 (逆时针旋转θ逐渐增大，顺时针旋转θ逐渐减小)
  * y轴 matrix(cosθ, 0, sinθ, 0, -sinθ, 1, cosθ, 0, 0, 0, 0, 0, 0, 0, 0, 1) 旋转θ度 (逆时针旋转θ逐渐增大，顺时针旋转θ逐渐减小)
  * z轴 matrix(cosθ, sinθ, 0, 0, -sinθ, cosθ, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1) 旋转θ度 (逆时针旋转θ逐渐增大，顺时针旋转θ逐渐减小)
* 复核变换矩阵 图形中心缩放n倍，旋转θ度，平移tx, ty, tz之后的矩阵
  * x轴 matrix(n, ncosθ, nsinθ, 0, 0, -nsinθ, ncosθ, 0, 0, 0, 0, 0, tx, ty, tz, 1)
  * y轴 matrix(ncosθ, 0, nsinθ, 0, -nsinθ, n, ncosθ, 0, 0, 0, 0, 0, tx, ty, tz, 1)
  * z轴 matrix(ncosθ, nsinθ, 0, 0, -nsinθ, ncosθ, 0, 0, 0, 0, n, 0, tx, ty, tz, 1)

#### perspective 属性指定了观察者与z=0平面的距离，使具有三维位置变换的元素产生透视效果。z>0的三维元素比正常大，而z<0时则比正常小.可用在父元素上， 也可以用在自己身上。
* __`80px`__

#### perspective-origin 属性指定了观察者的位置，在属性perspective中被用作消失点
* __`50% 50%`__
* __`center left`__
* __`80px 90px`__

#### transform-style
* __`preserve-3d`__ 指定子元素定位在三维空间内。
* __`flat`__ 指定子元素位于此元素所在平面内。

#### backface-visibility
* __`visible`__ 表示背面可见，允许显示正面的镜像。
* __`hidden`__ 表示背面不可见。