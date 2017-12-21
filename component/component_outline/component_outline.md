# 组件使用

## 说明

quick中除了框架API外还有按需使用的组件API

每一个组件的API都需要遵循如下步骤才能使用

## 第一步：获取组件的别名

需要从相应的原生容器配置中，获取对应的组件别名

譬如: 

```js
pay
ui
page
...
```

这些都是对应组件的别名，当然了，框架组件无需再注册（因为默认已经注册）

## 第二步：注册组件

__组件使用前必须先注册__

```js
quick.error(function(error) {
    // 添加自己的错误提示
});

quick.config({
    // 这里可以是任意需要注册的别名数组
    jsApiList: ['pay'],
});
// initPage是页面初始函数
quick.ready(initPage);
```

__注意⚠️:必须容器支持该组件才能注册成功，否则注册失败__

##  第三部：调用API

注册成功后即可在需要的时候调用API

```js
quick.callApi({
    // 该组件下的任意api
    name: "api1",
    mudule: 'moduleName',
    // 是否长期回调，为0时可以省略
    isLongCb： 0,
    data: {
        // 任意键值
        key1: value1,
    },
    success: function(result) {
        // 处理成功
    },
    error: function(error) {
        // 处理失败
    }
});
```

__注意⚠️：如果是长期回调，`isLongCb`请传`1`__