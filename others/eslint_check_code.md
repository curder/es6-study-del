# 利用 ESLint 检查代码质量

## 介绍 ESLint

JavaScript 是一门神奇的动态语言，它在带给我们编程的灵活性的同时也悄悄埋下了一些地雷。除了基本的语法错误能在程序一启动的时候被检测到之外，很多隐含的错误都是在运行的时候才突然地蹦出来。而为了避免这样的错误可能你只需要在提交代码的时候用工具静态分析一下。

[ESLint](http://eslint.cn/ "ESLint 官网") 是一个插件化的 JavaScript 代码检测工具，它可以用于检查常见的 JavaScript 代码错误，也可以进行代码风格检查，这样我们就可以根据自己的项目需求指定一套 ESLint 配置，然后应用到所编写的项目上，从而实现辅助编码规范的执行，有效控制项目代码的质量。

## 安装

在开始使用 ESLint 之前，通过 NPM 命令安装它

```
npm i -g eslint
```

> 上面的命令表示在系统全局环境安装 ESLint。

## 配置

```
eslint --init
```

> `eslint --init` 适用于对某个项目进行设置和配置 ESLint，并在其运行的的目录执行本地安装的 ESLint 及 插件。
> 如果倾向于使用全局安装的 ESLint，配置中使用的任何插件也必须是全局安装的。

更多配置[参考这里](http://eslint.cn/docs/user-guide/getting-started#configuration)

常见配置如下

```

```