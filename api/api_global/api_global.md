# quick.global

一些全局API，通过`quick.method()`即可调用

## config

初始化校验，必须调用

注，如果没有`组件API`需要注册，可以传空，注册组件时，必须容器支持对应组件才能注册成功

同时，`config`内部也会进行一些其它验证，譬如`白名单验证`（根据实际需求而定），如果没有通过验证，则无法触发`ready`

另外，在`H5`下降级成为调用后直接触发`ready`回调

```js
quick.config({
    // 需要注册的模块别名数组
    jsApiList: ['pay']
});
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| jsApiList | Array[String] | 需要注册的组件API信息，除了框架中的组件外，其它新增的组件使用时都需要通过这个入口注册 |


__环境支持__

`H5`、`quick`

## ready

验证成功后的回调，`quick.ready`参数为回调函数，在验证成功后会触发，任何相关操作请在回调函数后执行

如果验证失败，不会走`ready`，而是会走`error`

```js
quick.ready(function() {
    // TODO: 处理成功后的逻辑，需要权限的API只有在ready触发后才能被正确调用
});
```

__环境支持__

`H5`、`quick`

## error

处理错误信息，`quick.error`参数为回调函数，在容器或`quick`框架捕获到错误时，都会触发这个回调

```js
quick.error(function(error) {
    // TODO: 可以捕获相应的错误，例如，验证失败会触发error，原生容器捕获到异常错误也会触发
    alert("error: " + JSON.stringify(err));
});
```

__返回说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| code | Number | 错误代码 |
| message | String | 错误的详细说明信息 |

__环境支持__

`H5`、`quick`

## callApi

调用自定义API，只能调用`quick`环境下的API

注，请不要调尝试用框架标准API

```js
quick.callApi({
    name: 'API的名字', // 例如 alert（仅举例）
    mudule: 'API的模块名', // 例如 ui（仅举例）
    isLongCb: 0, // 是否是长期回调
    data: {}, // 需要传递给原生的数据
    success: function(result) {
        /**
         * 长期回调的情况下，每次符合条件都会触发
         * 短期回调的情况下，只会触发一次
         * 回调的参数由具体的自定义API决定
         */
    },
    error: function(error) {}
});
```

__返回说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| name | String | API的名称 |
| mudule | String | API对应的模块 |
| isLongCb | Number | 是否是长期回调，`1`代表长期回调，`0`代表短期回调，短期回调调用一次后会自动回收，长期回调可以一直触发，默认为`0` |
| data | JSON | 需要传递给原生的数据，例如`{key1: "value1"}`，具体数据由对应API决定 |


__环境支持__

`quick`

