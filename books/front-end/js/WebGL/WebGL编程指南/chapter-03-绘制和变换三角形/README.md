# 绘制和变换三角形
### 不管三维模型多么复杂，其基本组成部分都是三角形。
#### __`缓存区对象`__ 他可以一次性的向作色器传入多个顶点数据。缓冲区对象是WebGL系统中的一块内存区域。我们可以一次性的向缓冲区对象中传入大量的顶点数据，然后将这些数据保存在其中，供顶点着色器使用。
### 对于简单的变换，你可以使用数学表达式来实现。但是对于情形变的逐渐复杂时，你很快发现表达式运算实际上相当繁琐。
## WebGL个OpenGL 矩阵元素都是按列主序
```
逆时针旋转矩阵()
[
    cosB, sinB, 0.0, 0.0,
    -sinB, cosB, 0.0, 0.0,
    0.0, 0.0, 1.0, 0.0,
    0.0, 0.0, 0.0, 1.0
]
平移矩阵
[
    1.0, 0.0, 0.0, 0.0,
    0.0, 1.0, 0.0, 0.0,
    0.0, 0.0, 1.0, 0.0,
    Tx, Ty, Tz, 1.0
]
缩放矩阵
[
    Sx, 0.0, 0.0, 0.0,
    0.0, Sy, 0.0, 0.0,
    0.0, 0.0, Sz, 0.0,
    0.0, 0.0, 0.0, 1.0
]
```
```javascript
   let vertexColorBuffer = gl.createBuffer(); // 第一步: 创建缓冲区对象
   let a_Position = gl.getAttribLocation(gl.program, 'a_Position'); // 顶点位置

   // gl.ARRAY_BUFFER 表示缓冲区对象中包含了顶点的数据
   gl.bindBuffer(gl.ARRAY_BUFFER, vertexColorBuffer); // 第二步: 将缓存区对象(vertexColorBuffer)绑定到目标
   // gl.STATIC_DRAW 只会向缓冲区中写入一次数据 但需要绘制很多次
   gl.bufferData(gl.ARRAY_BUFFER, verticesColors, gl.STATIC_DRAW); // 第三步: 向缓存区对象写入数据
   gl.vertexAttribPointer(a_Position, 2, gl.FLOAT, false, FSIZE*5, 0); // 第四步: 将缓存区对象分配给a_position
   gl.enableVertexAttribArray(a_Position); // 第五步: 连接a_Position变量与分配给它的缓存区对象
```