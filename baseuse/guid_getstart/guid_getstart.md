# 开始开发

## 第一步: 页面引入js文件

引入`quick`的核心库，必须引入，引入后会得到一个全局变量`quick`(支持amd、cmd方式引入)

```html
<script src="xxx/quick.js"></script>
```

引入`quick`环境的API支持库:

```html
<script src="xxx/quick.native.js"></script>
```

引入`H5`环境的API支持库:

```html
<script src="xxx/quick.h5.js"></script>
```

注意，`quick`，`H5`等API支持库请按需引入


## 第二步: 页面初始化

`quick`页面，必须通过如下几步进行初始化

更多参考 [quick全局调用](../../api/api_global/api_global.md)

```js
quick.error(function(error) {
    alert(JSON.stringify(error));
});

quick.config({
    // 可以传入需要注册的拓展组件-如果原生有支持的话，也可以不传
    jsApiList: ['pay']
});
quick.ready(function() {
    // TODO: 处理验证成功后的事情，例如调用api
});
```