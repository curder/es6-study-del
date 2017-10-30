## 在ES5中渲染一个模板

```
var tpl = '<div>' +
'<span>'+title+'</span>'
'</div>';
```

## 在ES6中渲染一个模板

```
let title = 'Title Code';
let tpl = `
<div>
    <span>${title}</span>
</div>
`;
```

> 使用反引号模板，使用`${}`将变量渲染,并且会将渲染结构保留