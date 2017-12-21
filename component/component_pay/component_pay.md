# Pay组件

## 功能说明

该组件功能是示例中集成的测试用例，仅用来验证组件拓展流程

## 别名

别名：（请不要更改）

```js
pay
```

## testPay

测试字符，调用后立马会成功回调

```js
quick.callApi({
    name: "testPay",
    mudule: 'pay',
    success: function(result) {
        /**
         * {
                message: ''
           }
         */
    },
    error: function(error) {
        // 处理失败
    }
});
```

__返回说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| message | String | 返回提示 |

