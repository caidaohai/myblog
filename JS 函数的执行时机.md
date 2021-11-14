## JS函数的执行时机
JS函数调用的时机不同，得到的结果不同。
```js
var a = 1;
function fn(){
    console.log(a);
}

fn();//打印1

a = 2;
fn();//打印2
```
在上面的例子中，第一次调用fn函数时，打印a，此时a的值为1,此时`console.log(a)`便打印出此时的值1;当第二次调用fn函数时，a的值已经变成了2，此时`console.log(a)`便打印出此时的值2;

下面的例子
```js
for(var i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```
在上述例子中，for循环中的代码循环执行了6次，`setTimeout`是一个定时函数，它的意思是，当执行完当前程序之后再执行`setTimeout`中的代码，因此当`setTimeout`中的代码被执行时，此时`i`的值已经变为了6,因此上述代码会打印出6个6.

那么如何打印出0到5的值呢?js中使用`let`定义`for`循环的初始化表达式,即可得到0到5的值，代码如下
```javascript
for(let i = 0;i<6;i++){
    setTimeout(()=>{
        console.log(i)
    },0)
}
```

除此之外，还可以使用立即执行行数得到相同的效果，代码如下
```javascript
 for (var i = 0;i<6;i++){
     !function(i){
       setTimeout(()=>{
            console.log(i)
        },0)  
     }(i)
 }   

```
