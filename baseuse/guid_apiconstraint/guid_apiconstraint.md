# API约束

## 调用示例

```js
quick.模块名.方法({
    参数1: "",
    参数2: "",
    success: fucntion(result) {
        // 成功回调
    },
    error: fucntion(error) {
        // 失败回调
    }
});
```

### 接口约定

- 所有接口都为异步调用

- 接收一个`object`类型的参数

- 成功回调`success`

    - 通过`result`获取成功数据
    
    - 回调函数的触发时机由具体的API决定，有的API是调用时即可回调，有的是某个事件触发后才被回调

- 失败回调`error`，所有的API调用错误都会走失败回调
