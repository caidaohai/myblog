# css知识总结

## 一、浏览器渲染原理
### 步骤
1. 根据HTML构建HTML树 (DOM)
2. 根据CSS构建 CSS树 (CSSOM)
3. 将两棵树合并成一颗渲染树 (render tree)
4. Layout布局(文档流、盒模型、计算大小和位置)
5. Paint绘制(把边框颜色、文字颜色、阴影等画出来)
6. Compose 合成 （根据层叠关系展示画面）

### 三种不同的渲染方式
![渲染图](https://caidaohai.github.io/myblog/images/cssRender.png)

1. 第一种，例如：div.remove() ，会触发当前消失，其他元素 relayout
2. 第二种，例如：改变颜色，直接 repaint + composite
3. 第三种，例如：改变改变 transform ，只需 composite

## 二、CSS 动画的两种做法（transition 和 animation）
## <strong>a.transform transition 过渡完成动画</strong>
### <b>transform</b>
四个常用功能
* 位移 translate
* 缩放 scale
* 旋转 rotate
* 倾斜 skew

注意：这些功能一般都需要配合 transition 过渡。inline 不支持 transform，需要先变成 block

### <strong>translate</strong>
* <code>translateX(\<length-percentage\>)</code>
* <code>translateY(\<length-percentage\>)</code>
* <code>translate(\<length-percentage>\<length-percentage>?)</code>
* <code>translateZ(\<length\>) 且父容器 perspactive</code>
* <code>translate3d(X, Y, Z)</code>

translate(-50%, -50%) 可做绝对定位元素的居中

### <strong>scale</strong>
* <code>scaleX(\<number>)</code>
* <code>scaleY(\<number>)</code>
* <code>scale(\<number>, \<number>?)</code>

### <strong>rotate</strong>
* <code>rotate([\<angle> | \<zero>]</code>
* <code>rotateX([\<angle> | \<zero>])，以 X 轴旋转</code>
* <code>rotateY([\<angle> | \<zero>])，以 Y 轴旋转</code>
* <code>rotateZ([\<angle> | \<zero>])，以 Z 轴旋转</code>
* <code>rotate3d([\<angle> | \<zero>])</code>

### <strong>skew</strong>
* <code>skewX([\<angle> | \<zero>])</code>
* <code>skewY([\<angle> | \<zero>])</code>
* <code>skew([\<angle> | \<zero>], [\<angle> | \<zero>]?)</code>

### <strong>transition 过渡</strong>
### <b>作用</b>

补充中间帧

### <b>语法</b>
* transition: 属性名 时长 过渡方式 延迟
* transition: left 200ms linear
* transition: left 200ms, top 400ms 可以用逗号分隔两个不同的属性
* transition: all 200ms 可以用 all 代表所有属性
* 过渡方式有：linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier | step-start | step-end | steps

### <b>注意</b>
并不是所有属性都能过渡

* display: none => block 没法过渡
* 一般改成 visibility: hidden => visible

过渡必须要有起始:比如 hover 和 非 hover 就是两次动画,如果有中间点，可以通过下列两种方法解决
1. 使用两次 transform

    .a === transform ===> .b<br />
    .b === transform ===> .c
2. 使用 animation

    声明关键帧<br />
    添加动画

## <strong>animation完成动画</strong>
### <b>@keyframes 完整语法</b>
* 一种写法是 from to
```
    @keyframes xxx{
        from{
            transform: translateX(0%);
        }
        to{
            transform: translateX(100%);
        }
    }
```
* 另一种写法是百分数
```
@keyframes xxx{
    0%{
        transform: none;
    }
    66.66%{
        transform: translateX(200px);
    }
    100%{
        transform:translateX(200px)translateY(100px);
    }
}
```
### <b>animation 缩写语法</b>
animation: 时长 | 过渡方式 | 延迟 | 次数 | 方向 | 填充模式 | 是否暂停 | 动画名;

* 时长：1s 或 1000ms
* 过渡方式：跟 transition 取值一样
* 次数：3 或者 2.4 或者 infinite
* 方向：reverse | alternate | alternate-reverse
* 填充模式：none | forwards | backwards | both
* 是否暂停：paused | running
* 以上所有属性都有对应的单独属性



