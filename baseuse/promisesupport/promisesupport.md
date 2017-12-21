# Promise支持

`quick`中，大部分API都支持`Promise`

注，有少部分API不支持`Promise`

## 不支持`Promise`的API

有少部分API因为涉及到多次回调（比如右上角按钮），所以不建议使用`Promise`

如果强行要使用，这些API调用完毕后马上就会进入`then`

以下是不支持`Promise`的长期回调`API`

| JSAPI | 说明 |
| :------------- |:-------------|
| navigator.hookSysBack | 拦截系统返回按钮 |
| navigator.hookBackBtn | 拦截左侧导航栏返回按钮 |
| navigator.setRightBtn | 设置并监听右侧按钮 |
| navigator.setLeftBtn | 设置并监听左侧按钮 |
| navigator.setRightMenu | 设置并监听右侧下拉菜单 |

另外，一些全局调用，由于性质不一样，也不支持`Promise`，如

- `quick.config`，`quick.ready`，`quick.error`

## 支持`Promise`的API调用示例

注，除了不支持列表中的API，其它都支持`Promise`用法

### 基本用法

```js
quick.ui.alert({
    title: '提示',
    message: 'sd#ddd测试',
    success: function(result) {
        litemplate.showTips(JSON.stringify(result));
    },
    error: function(error) {
        litemplate.showTips('失败:' + JSON.stringify(error));
    }
});
```

### Promise用法

```js
quick.ui.alert({
    message: "hello",
}).then(function(result) {
    console.log('点击alert成功，进入then');
}).catch(function(error) {
    console.error('失败:' + JSON.stringify(error));
});
```

## 自定义API调用也支持`Promise`

除了标准`API`外，调用自定义API`quick.callApi`也支持`Promise`

### 使用示例

```js
// 实际中请不要这样调用标准API，这里仅作为示例
// 因为标准API除了调用外还有可能有其它的兼容处理，直接callApi无法达到那个目的
quick.callApi({
    name: "pickDate",
    mudule: 'ui',
    data: {
        datetime: '2017-07-25'
    }
}).then(function(result) {
    console.log('成功选择时间：' + JSON.stringify(result) + ',进入then');
}).catch(function(error) {
    console.error('失败:' + JSON.stringify(error));
});
```

- `callApi`也一样支持基本用法

- 另外，当参数`isLongCb = 1`时，和最前面的长期回调一样，这时候`callApi`也同样不支持`Promise`