## 复合变换
### 平移后选择
#### <旋转矩阵> * (<平移矩阵> * <原始坐标>) = <旋转矩阵> * <平移矩阵> * <原始坐标>
### requestAnimationFrame() 该方法只有在标签页处于激活状态时才会生效 返回一个id 无法指定重复调用的间隔
### cancelAnimationFrame(id) 根据id取消requestAnimationFrame方法
```javascript
// Start drawing
  var tick = function() {
    currentAngle = animate(currentAngle);  // Update the rotation angle
    draw(gl, n, currentAngle, modelMatrix, u_ModelMatrix);   // Draw the triangle
    requestAnimationFrame(tick, canvas);   // Request that the browser ?calls tick
  };
  tick();
```