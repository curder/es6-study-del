# 字符串操作

在ES6中给我们带来了几个新增的字符串方法，它们分别是：`indexOf()`、`includes()`、`startsWith()`、`endsWith()`和`repeat()`。


## `indexOf`和`includes`查找

在ES5的写法中我们可能会用到 `indexOf()`来判断一个字符串中是否包含某个子字符串，如下：

```
console.log('Yo'.indexOf('a') !== -1); // false
console.log('Yo'.indexOf('Y') !== -1); // true
```

在ES6中，给我们带来了一个新的函数`includes()`方法，如下：

```
console.log('Yo'.includes('a')); // false 
console.log('Yo'.includes('Y')); // true
```

## `startsWith()`判断字符串是否以某个字符开始

在ES6之前要实现这个操作可能需要写一个方法，但是ES6默认支持这个写法，如下：

```
console.log('Yo'.startsWith('Y')); // true
console.log('Yo'.startsWith('o')); // false
```


## `startsWith()`判断字符串是否以某个字符结束

```
console.log('Yo'.endsWith('Y')); // false
console.log('Yo'.endsWith('o')); // true
```


## `repeat()`重复一个字符串

```
console.log('Yo '.repeat(10)); // 重复10次
```

# 其他

## 在ES6中，我们可以解包字符串的同时直接获取字符串的长度

```
let {length: StrLength} = 'Yo';
console.log(StrLength); // 此时获取到字符串的长度是 2
```