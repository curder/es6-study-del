# Var、Let和Const

## Var声明变量的特点

### var声明的变量是可以重复赋值和重复定义的

- 重复赋值

```
var price = 100;
price = 200;
console.log(price);
```

以上代码执行完正确打印`price`的值，200。

- 重复定义

```
var price = 100;
var price = 300;
console.log(price);
```

以上代码执行完正确打印`price`变量的值，300。

### var声明的变量是函数作用域

```
function getPrice(){
    var price = 1;
    console.log(price);
}
getPrice();
console.log(price);
```

以上代码执行后报错：`Uncaught ReferenceError: price is not defined`，说明在定义的函数`getPrice()`外无法访问函数内定义的变量`price`的值。

有时候我们在`if`等判断语句内定义一个临时变量，也不希望在`if`结构体外能访问，使用`var`声明的遍历则做不到。

```
var price = 100;
var count = 10;
if(count > 5) {
    var discount = price * .6;
    console.log(`The discount is ${discount}`);
}
console.log(discount); // 此时能访问在`if`结构体中运算的`discount`的值。
```

此时我们就需要借助 `let` 关键字，来定义**块级作用域**。

## let和const共同点

### 块级作用域

使用let、const声明的变量、常量作用域在块级内生效。
```
var price = 100;
var count = 10;
if(count > 5) {
    let discount = price * .6;
    console.log(`The discount is ${discount}`);
}
console.log(discount); // Uncaught ReferenceError: discount is not defined
```
 
关注到`discount`是在`if`结构体中使用`let`关键字声明的，此时在`if`结构体外无法

使用let声明的常量作用域在块级内生效。

```
var price = 100;
var count = 10;
if(count > 5) {
const discount = price * .6;
console.log(`The discount is ${discount}`);
}
console.log(discount); // Uncaught ReferenceError: discount is not defined
```


- let的这一特性常常用于定义一些局部变量。

```
{
const name = 'curder';
}
```

- 使用let来定义for循环中的变量

```
for (let i = 0; i < 10; i++) {
console.log(i);
setTimeout(function(){
console.log(`i:${i}`);
}, 1000);
}
```

由于`let`声明的变量是块级作用域，所以每次循环变量的值将只在for循环中生效。此时不能使用const关键字定义`i`常量。


### let和const在相同作用域中都不能重复定义常量或者变量

```
let status = 1;
let status = 2; // Uncaught SyntaxError: Identifier 'status' has already been declareds
```

重复声明同一个变量将报错。

```
const status = 1;
const status = 2; // Uncaught SyntaxError: Identifier 'status' has already been declared
```

重复声明同一个常量将报错。


### 其他情况

如果常量的值是引用类型的时候，我们可以修改常量的属性。

```
const person = {name: "curder", age: 22}

person.age = 23
```
此时打印`person`常量的值将得到修改后的结果。

如果此时却是不允许修改常量的属性，那么可以使用`Object.freeze(obj)`的方式申明常量。[参考这里](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze)

```
const user = Object.freeze({name: 'curder', age: 20});
```
