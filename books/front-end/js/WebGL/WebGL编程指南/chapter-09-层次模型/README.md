## 层次模型
#### 如果第一层做旋转操作，将模型矩阵保留，作用到第二层上，如果第二层还需要进行其他操作，就用矩阵叉乘。
## initShaders()函数
#### __`着色器对象`__ 着色器对象管理一个顶点作色器 __`或者`__ 一个片元着色器，每个着色器都有一个着色器对象。
#### __`程序对象`__ 程序对象是管理着色器对象的容器。在WebGL中，一个程序对象必须包含一个顶点着色器和一个片元着色器。
* 创建作色器对象 __let shader = gl.createShader(gl.VERTEX_SHADER)__
* 向着色器对象中填充着色器程序的源代码 __gl.shaderSource(shader, source)__
* 编译作色器 __gl.compileShader(shader)__
* 创建程序对象 __let program = gl.createProgram()__
* 为程序对象分配作色器 __ gl.attachShader(program, vertexShader)__
* 连接程序对象 __gl.linkProgram(program)__
* 使用程序对象 __gl.useProgram(program)__
  * 这个函数的存在使得webgl有一个强大的特性，那就是在绘制前准备准备多个程序对象，然后在绘制的时候根据需要切换程序对象。