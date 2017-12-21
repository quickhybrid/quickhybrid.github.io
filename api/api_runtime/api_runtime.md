# quick.runtime

## launchApp

打开第三方APP

```js
quick.runtime.launchApp({
    packageName: '',
    className: '',
    actionName: '',
    scheme: 'taobao://',
    data: 'testdata'
    success: function(result) {},
    error: function(error) {}
});
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| packageName | String | Android应用的包名 |
| className | String | Android应用页面类名 |
| actionName | String | Android应用页面配置的ActionName |
| scheme | String | 页面配置的Scheme名字，适用于Android与iOS |
| data | String | 传递的参数。需要目标应用解析获取参数。 |

__环境支持__

`quick`

## getAppVersion

获取容器版本号

```js
quick.runtime.getVersion({
    success: function(result) {
        /**
         * {
                version: '7.0.0'
           }
         */
    },
    error: function(error) {}
});
```

__返回说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| version | String | 容器的版本号 |

__环境支持__

`quick`

## getQuickVersion

获取容器的Quick版本号

注，是容器的Quick版本号，与前端的Quick版本号不一样，前端Quick版本号通过`quick.version`获取

```js
quick.runtime.getQuickVersion({
    success: function(result) {
        /**
         * {
                version: '3.0.0'
           }
         */
    },
    error: function(error) {}
});
```

__返回说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| version | String | 容器的Quick版本号 |

__环境支持__

`quick`

## getGeolocation

获取地理位置

```js
quick.runtime.getGeolocation({
    success: function(result) {
        /**
         * {
                longitude: "31.896201",
                latitude: "120.573466",
                addressComponent: {
                    "country": "中国", 
                    "country_code": 0,
                    "province": "江苏省",
                    "city": "苏州市",
                    "district": "张家港市",
                    "adcode": "320582",
                    "street": "一干河东路",
                    "street_number": "",
                    "direction": "",
                    "distance": ""
                }
           }
         */
    },
    error: function(error) {}
});
```

譬如国内`H5`百度地图默认接收的是火星坐标，否则会有偏差

一般手机`app`的默认获取定位是地球坐标（不通过三方SDK）

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| coordinate | Number | 默认为`1`，`1`代表火星坐标系`GCJ-02`（天朝特色，带偏差，国内高德坐标也是这个），`0`代表地球坐标系`WGS84`（标准坐标） |

__返回说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| longitude | String | 经度 |
| latitude | String | 维度 |
| addressComponent | Object | 详细的地理位置，内部包含详细的省市县等地理位置信息 |

__环境支持__

`quick`

## clearCache

清除容器缓存

相关缓存包括图片缓存等

```js
quick.runtime.clearCache({
    success: function(result) {},
    error: function(error) {}
});
```

__环境支持__

`quick`

## clipboard

复制文本信息到剪切板

```js
quick.runtime.clipboard({
    text: "",
    success: function(result) {},
    error: function(error) {}
});

// 支持快速调用
quick.runtime.clipboard("需要复制的文本");
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| text | String | 需要复制的文本 |

__环境支持__

`quick`

## openUrl

外部浏览器打开url

```js
quick.runtime.openUrl({
    url: "https://www.baidu.com/",
    success: function(result) {},
    error: function(error) {}
});

// 支持快速调用
quick.runtime.openUrl("https://www.baidu.com/");
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| url | String | 需要被打开的url |

__环境支持__

`quick`