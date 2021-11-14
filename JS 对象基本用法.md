# JavaScript 对象的基本用户
## 一、对象的定义以及声明
对象是一组"键值对"(key-value) 的集合，是一种无序的复合数据集合。对象的声明有两种方法，一种是使用new关键字进行声明，如下
```javascript
let obj = new Object({
        'name':'john',
        'age':16
    });
```
还可以省略掉new和Object,直接使用大括号进行声明
```javascript
let obj = {
    'name':'john',
    'age':16
}
```
上面代码中，大括号就定义了一个对象，它被赋值给变量obj，所以变量obj就指向一个对象。该对象内部包含两个键值对（又称为两个“成员”），第一个键值对是`'name':'john'`，其中`name`是“键名”（成员的名称），字符串`john`是“键值”（成员的值）。键名与键值之间用冒号分隔。第二个键值对是`age: 16`，`age`是键名，16是键值。两个键值对之间用逗号分隔。

## 二、对象操作之删除对象的属性
可以使用delete命令来删除对象的属性.代码如下
```javascript
let obj = { p: 1 };
delete obj.p //true
Object.keys(obj) // []
```

## 三、对象操作之查看对象的属性
读取对象的属性，有两种方法，一种是使用点运算符，还有一种是使用方括号运算符。
```javascript
let obj = {
    p:'Hello World'
};

obj.p //使用点运算符,"Hello World"
obj['p']//使用方括号读取,"Hello World"
```
如果使用方括号运算符，键名必须放在引号里面，否则会被当作变量处理

```javascript
let foo ='bar';

let obj = {
    foo:1,
    bar:2
};

obj['foo'] //1
obj[foo] //2
```

查看一个对象本身的所有属性，可以使用Object.keys方法。
```js
let obj ={
  key1:1,
  key2:2
};
Object.keys(obj);
// ['key1', 'key2']
```

如果要查看自身属性和共有属性，可以使用`console.dir(obj)`在控制台打出

## 四、对象操作之修改或增加对象的属性
可以通过给对象的属性进行赋值来修改该属性，如果这个属性不存在，则会增加此属性
```javascript
   let obj = {
       'name':'ccc',
       'age':23
   }
   obj['sex'] = 'gender';//新增一个sex属性
   console.log(obj);
   //{name: "ccc", age: 23, sex: "gender"}

   obj['name'] = 'ddd';//修改name属性
   //{name: "ddd", age: 23, sex: "gender"}
```
如果想要改变共有属性，可以通过`Object`对象进行修改，譬如`Object.prototype['toString'] = 'xxx'`

如果想要改变原型对象，可以先定义一个对象，然后使用`Object.create()`进行更改
```js
let common = {
    'location':'beijing',
    'type':'IT'
}

let company = Object.create(common);
```
这样`company`的__proto__原型地址就指向了common对象

## 五、'name' in obj和obj.hasOwnProperty('name') 的区别
'name' in obj 可以判断某个属性是否属于obj对象，如果是原型所拥有的属性，也会返回true
```js
var person = {
    'height':176,
    'color':'yellow'
}
'height' in person;//true
'children' in person;//false
'toString' in person;//false
```
在上例中，`height`是`person`对象的属性，`'height' in person`因此返回true;

`children`不是对象`person`的属性`'children' in person`因此返回false

`toString`是`person`原型对象的属性，`'toString' in person`也返回了true

`obj.hasOwnProperty('name')`只返回obj对象自有的属性
```js
var person = {
    'height':176,
    'color':'yellow'
}
person.hasOwnProperty('height');//true
person.hasOwnProperty('children');////false
person.hasOwnProperty('toString');//false
```


