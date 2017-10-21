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

## let变量的特点

### 块级作用域

使用let声明的变量作用域在块级内生效。

```
var price = 100;
var count = 10;
if(count > 5) {
    let discount = price * .6;
    console.log(`The discount is ${discount}`);
}
console.log(discount); // Uncaught ReferenceError: discount is not defined
```

## conset常量的特点

### 块级作用域

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



