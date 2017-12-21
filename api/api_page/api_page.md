# quick.page

## open

新窗口打开一个页面

注意，新页面会默认读取页面的`title`并设置

`H5`下是兼容情况，仅剩下打开页面以及传递参数功能，配置无法生效

```js
quick.page.open({
    pageUrl: "./quick_demo_v3_simple.html",
    pageStyle: 1,
    orientation: 1,
    data: {
        key1: 'value1'
    },
    success: function(result) {
        /**
         * 目标页面关闭后会触发这个回调，参数是页面通过close传递过来的参数
         * {
                resultData: '可能是json，也可能是普通字符串，要看怎么传参的'
           }
         */
        
    },
    error: function(error) {}
});

// 兼容快速调用
quick.page.open("./quick_demo_v3_simple.html", {
    key1: 'value1'
});
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| pageUrl | String | 目标页面的地址，支持`http或https或//`开头的网络路径，也支持`./或../`开头的相对路径，也支持`pages/xxx`开头的绝对路径，绝对路径的方式下要求当前页面必须在`pages`文件夹中(如`pages/a.html`)，否则会计算错误 |
| orientation | Number | 是横屏打开还是竖屏打开，`1`为竖屏，`0`为横屏，默认为`1`,`-1`为跟随系统 |
| pageStyle | Number | 页面的类型，有多种类型，`1`为默认类型，参考`pageStyle参数说明` |
| data | JSON | 需要传递的参数，`JSON`键值对形式 |

__pageStyle参数说明__

| 值 | 说明 |
| :------------- |:-------------|
| -1 | 隐藏导航栏的页面类型 |
| 1 | `默认值`，默认导航栏类型的页面 |

__环境支持__

`H5`、`quick`

## openLocal

打开应用内原生页面

```js
// 示例页面不一定可以打开，仅供参考
var className = quick.os.android ? 'com.epoint.demo.view.ComponentCaseActivity' : 'EPTFileSelectViewController';

quick.page.openLocal({
    className: className,
    isOpenExist: 0,
    data: {
        key1: 'value1'
    },
    success: function(result) {
        /**
         * 目标页面关闭后会触发这个回调
         * 参数需要原生页面主动设置result才能正常返回
         * {
                resultData: '可能是json，也可能是普通字符串，要看怎么传参的'
           }
         */
        
    },
    error: function(error) {}
});
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| className | String | 页面的类名，`Android`和`iOS`下有差异 |
| isOpenExist | Number | 是否打开已经存在的页面并且页面置顶，如果为`1`，会杀掉栈内该页面上面的所有页面(比如有`A->B->C`，如果打开`B`并且设置`1`，那么`A`页面会被杀掉)，默认为`0` |
| data | JSON | 需要传递的参数，`JSON`键值对形式，键值对不能再嵌套子`JSON` |

__环境支持__

`quick`

## close

关闭页面

在`H5`下只支持普通的关闭，无法传参

```js
quick.page.close({
    // 也支持传递字符串
    resultData: {
        key: 'value2'
    },
    success: function(result) {
        /**
         * 回调内请不要做UI显示相关的事情
         * 因为可能刚回调页面就关闭了
         */
        
    },
    error: function(error) {}
});

// 兼容快速调用(快速调用只支持字符串)
quick.page.close(JSON.stringify({key: 'value2'}));
quick.page.close('value2');
```

__参数说明__

| 参数 | 参数类型 | 说明 |
| :------------- |:-------------:|:-------------|
| popPageNumber | Number | 需要关闭的页面层级，默认为`1`，只会关闭一层 |
| resultData | String或JSON | 需要传递给上一个页面的数据，可以是`JSON`格式数据或者是普通字符串数据 |

__环境支持__

`H5`、`quick`

## reload

重新加载页面

```js
quick.page.reload();
```

__环境支持__

`H5`、`quick`
