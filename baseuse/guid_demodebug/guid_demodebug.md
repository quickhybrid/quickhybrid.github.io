# Demo

提供了一个在线Demo以及调试容器给开发提供方便，方便用来测试`quick`的API与容器

## PC调试页面

PC端写代码，移动端执行

[https://quickhybrid.github.io/quickhybrid/examples/debugapi/debugroom.html](https://quickhybrid.github.io/quickhybrid/examples/debugapi/debugroom.html)

基于socket.io，原理参考：

[http://www.dailichun.com/2017/11/28/socket_hybriddebug.html](http://www.dailichun.com/2017/11/28/socket_hybriddebug.html)

## 标准API示例

[https://quickhybrid.github.io/quickhybrid/examples/](https://quickhybrid.github.io/quickhybrid/examples/)

![](images/qrcode_js.png)

## 调试容器

__Android__

[https://www.pgyer.com/WGRn](https://www.pgyer.com/WGRn)

![](images/qrcode_android.png)

__iOS__

待续...


## 调试步骤

- 手机上下载对应系统的调试容器

- 打开扫一扫页面，并扫描Demo在线地址的二维码

- 进入在线Demo查看效果，首先确保正常调用

    - 如果调用出问题，可能是容器和Demo版本不匹配，可以反馈

- 确保上述正常后，用调试容器扫一扫实际项目中需要测试的`quick`页面

    - 如果出现问题，证明页面可能存在逻辑错误，请检查代码
    
    - 如果调试容器没问题，但是实际容器有问题，可能实际容器版本较低，请反馈
    