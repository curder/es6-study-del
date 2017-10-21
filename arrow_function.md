# ES6中的箭头函数

- 简明的语法

- 可以隐式返回

- 不绑定`this`

## 箭头函数简介的语法

相比匿名函数，箭头函数在函数的书写时删除了`function`关键字，增加了`=>`。

在传参的时候，如果只有一个参数，`()`可以不写；

如果有多个参数，`()`必须填写，并且多个参数之间使用`,`分割；

如果返回值只有一个return语句，则可以省略`{}`。


假如有一个如下数组，请将数组的每个元素*2。

```
const array = [10, 20, 30, 40, 50];
```

* 使用匿名函数的写法
```
let result = array.map(function(number){
    return number * 2;
});
console.log(result);
```

* 使用箭头函数改写
```
result = array.map((number) => {
    return number * 2;
});
console.log(result);
```

- 如果箭头函数只有一个参数可以省略`()`
```
resule = array.map(number => {
    return number * 2;
});
console.log(result);
```

- 如果返回值也只有一个return语句，可以将`{}`省略不写
```
result = array.map(number => number * 2);
console.log(result);
```

- 如果箭头函数存在多个参数时，必须写`()`，且参数使用`,`分隔
```
result = array.map((number, i) => `${i}: ${number * 2} `);
console.log(result);
```

