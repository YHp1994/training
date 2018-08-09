## HTML5陀螺仪
陀螺仪又叫角速度传感器，是不同于加速度计（G-sensor）的，他的测量物理量是偏转、倾斜时的转动角速度。在手机上，仅用加速度计没办法测量或重构出完整的3D动作，测不到转动的动作的，G-sensor只能检测轴向的线性动作。但陀螺仪则可以对转动、偏转的动作做很好的测量，这样就可以精确分析判断出使用者的实际动作。而后根据动作，可以对手机做相应的操作！

###### 获取旋转角度

x轴为轴，beta的作用域为(-180, 180)。

y轴为轴，gamma的作用域为(-90, 90)。

z轴为轴，alpha的作用域为(0, 360)。
```
 if (window.DeviceOrientationEvent) {
                window.addEventListener('deviceorientation', function (e) {
                    var a = document.getElementById('alpha'),
                        b = document.getElementById('beta'),
                        g = document.getElementById('gamma'),
                        alpha = e.alpha,
                        beta = e.beta,
                        gamma = e.gamma;
         
                    a.innerHTML = alpha;
                    b.innerHTML = beta;
                    g.innerHTML = gamma;
         
                }, false);
            } else {
                document.getElementById('tip').innerHTML = '你的浏览器不支持陀螺仪';
            }
```


1.deviceorientation 
设备的物理方向信息，表示为一系列本地坐标系的旋角。

2.devicemotion
提供设备的加速信息

3.compassneedscalibration
 用于通知Web站点使用罗盘信息校准上述事件
 
######  
###### 获取罗盘校准
https://blog.csdn.net/jaswhen/article/details/48526327

```
window.addEventListener(“compassneedscalibration", function(event) {
      alert('您的罗盘需要校准');
      event.preventDefault();
  }, true);
```
###### 获取重力加速度

```
window.addEventListener("devicemotion", function(event) {
   // 处理event.acceleration
   //	x(y,z):设备在x(y,z)方向上的移动加速度值
   //event.accelerationIncludingGravity
   //考虑了重力加速度后设备在x(y,z)
   // event.rotationRate
	//alpha,beta,gamma:设备绕x,y,z轴旋转的角度
  }, true);
```
## CSS3 3D模型
淘宝造物节


## 集合Touch事件

```
viewer.on('touchstart', function(e) {
    x1 = e.targetTouches[0].pageX;  //$(this).offset().left;
    y1 = e.targetTouches[0].pageY;  //$(this).offset().top;
});
viewer.on('touchmove',function(){
    var dist_x = x2 - x1,
        dist_y = y2 - y1,
        deg_x = Math.atan2(dist_y, perspective) / Math.PI * 180,
        deg_y = -Math.atan2(dist_x, perspective) / Math.PI * 180,
        i,
        c_x_deg += deg_x;
        c_y_deg += deg_y;
        
    cube.css('transform', 'rotateX(' + deg_x + 'deg) rotateY(' + deg_y + 'deg)');
})
```
###### CSS3D库
http://tridiv.com/app/

 
 

