## 需求描述

请实现一个打飞机游戏，玩家通过键盘方向键来控制飞机的移动，射击不断出现的敌机，并躲避敌机的冲击。效果如下：

![game.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8cd29e8246d54a109130bbeb3edc027c~tplv-k3u1fbpfcp-watermark.image?)

## 任务步骤

### 1. 技术栈选项

HTML5、CSS3、Canvas、JavaScript

### 2. 背景

利用「首尾相接」技巧，使用提供的背景图片做循环滚动，实现向前行驶的效果。

### 3. 子弹

- 初始位置：以所属飞机位置为基准
- 飞行效果：一旦发射，垂直方向移动，水平方向不变
- 回收机制：对于频繁创建和销毁的对象，可利用对象池进行内存优化

### 4. 敌机

敌机随机初始位置，并选用合理的回收机制

### 5. 碰撞检测

- 检测一：子弹与敌机的碰撞
- 检测二：敌机与主角的碰撞

## 编码阶段

`playGame.html` 初始代码如下：

```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <style>
        #map,#aircraft{
            position: absolute;
        }
        #aircraft{
            top: 0;
            left: 0;
            z-index: 2;
        }
        #map{
            background: url("beijing.jpg");
            -webkit-animation: mapscroll linear 10s infinite;
        }
        @-webkit-keyframes  mapscroll {
            0%{
                background-position: 0 0;
            }
            100%{
                background-position: 0 800px;
            }
        }
    </style>
</head>
<body>
<div style="position: relative">
    <canvas id="map" width="300" height="400"></canvas>
    <canvas id="aircraft" width="300" height="400"></canvas>
</div>

<script>
    //1. 定义图片资源的数组：预加载 imgonload (敌人飞机、你的飞机)
    //2. init 初始化的方法。方法里面 实例化飞机、实例化敌人、我的子弹
    //3. 构建玩家，我方飞机。属性：x,y,w,h 方法：move（）、top()、down()、left()、right()
    //4. 我方飞机，自带绘制图像，添加一个事件侦听：37-40 上下左右
</script>


</body>
</html>
```
