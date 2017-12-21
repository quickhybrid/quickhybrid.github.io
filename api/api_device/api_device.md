# quick.device

## setOrientation

设置屏幕方向

```js
quick.device.setOrientation({
    orientation: 1,
    success: function(result) {},
    error: function(error) {}
});
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| orientation | Number | `必填`，屏幕方向，`1`表示竖屏，`0`表示横屏，其他表示跟随系统,`-1`为跟随系统 |

__环境支持__

`quick`

## getDeviceId

获取设备ID

```js
quick.device.getDeviceId({
    success: function(result) {
        /**
         * {
                deviceId: ''
           }
         */
    },
    error: function(error) {}
});
```

__返回说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| deviceId | String | 对应的设备唯一ID |

__环境支持__

`quick`

## getNetWorkInfo

获取网络状态

```js
quick.device.getNetWorkInfo({
    success: function(result) {
        /**
         * {
                netWorkType: 1
           }
         */
    },
    error: function(error) {}
});
```

__返回说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| netWorkType | Number | 网络状态，`1`代表`wifi`,`0`代表移动网络，`-1`代表无网络 |

__环境支持__

`quick`

## getVendorInfo

获取设备厂商信息

同时将设备其它信息也一起返回

```js
quick.device.getVendorInfo({
    success: function(result) {
        /**
         * {
                netWorkType: 'xxx',
                deviceId: 'xxx',
                pixel: '1080*1920',
                uaInfo: 'android HUAWEI VTR-AL00'
           }
         */
    },
    error: function(error) {}
});
```

__返回说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| netWorkType | Number | 网络状态，`1`代表`wifi` |
| deviceId | String | 对应的设备唯一ID |
| pixel | String | 屏幕的像素信息，宽高以`*`分隔 |
| uaInfo | String | 厂商信息 |

__环境支持__

`quick`

## callPhone

拨打电话

```js
quick.device.callPhone({
    phoneNum: "182xxxxxxxx",
    success: function(result) {},
    error: function(error) {}
});

// 兼容快速调用
quick.device.callPhone('182xxxxxxxx');
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| phoneNum | Number | 需要拨打的电话号码 |

__环境支持__

`H5`、`quick`

## sendMsg

发送短信

```js
quick.device.sendMsg({
    phoneNum: "182xxxxxxxx",
    message:'hello',
    success: function(result) {},
    error: function(error) {}
});

// 兼容快速调用
quick.device.sendMsg('182xxxxxxxx', 'hello');
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| phoneNum | Number | 目标的电话号码 |
| message | String | 短信内容 |

__环境支持__

`H5`、`quick`

## closeInputKeyboard

关闭输入法软键盘，如果已经打开，则关闭

```js
quick.device.closeInputKeyboard({
    success: function(result) {},
    error: function(error) {}
});
```

__环境支持__

`quick`

## vibrate

调用原生的震动功能

```js
quick.device.vibrate({
    duration: 500,
    success: function(result) {},
    error: function(error) {}
});

// 支持快速调用
quick.device.vibrate(500);
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| duration | Number | 只在`Android`中有用，`iOS`中请忽略，震动的持续时间，单位是毫秒，默认是`500` |

__环境支持__

`quick`