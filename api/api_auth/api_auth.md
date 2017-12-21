# quick.auth

## getToken

注意，示例项目中这个字段是写死的，实际上需要自行补全逻辑

获取`token`，标准接口需要`token`才能正常请求

```js
quick.auth.getToken({
    success: function(result) {
        /**
         * {
                token: ''
           }
         */
    },
    error: function(error) {}
});
```

__返回说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| token | String | 对应的`token`，必须登录后才会有，`token`的刷新由原始容器进行，无需关心 |

__环境支持__

`quick`
