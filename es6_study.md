# Var、Let和Const

## Var声明变量的特点

### var声明的变量是可以重复赋值和重复定义的。
- 重复赋值

```
var price = 100;
price = 200;
console.log(price);
```

以上代码执行完正确打印price的值，200。

- 重复定义

```
var price = 100;
var price = 300;
console.log(price);
```

以上代码执行完正确打印price变量的值，300。

### var声明的变量是函数作用域

```
function getPrice(){
    var price = 1;
    console.log(price);
}
getPrice();
console.log(price);
```

以上代码执行后报错：`Uncaught ReferenceError: price is not defined`





