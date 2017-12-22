# 架构

## 多平台支撑架构图

![](images/quickhybrid_multiplatform.png)

## quick容器架构图

![](images/quickhybrid_apiimpl.png)

## 多平台支撑说明

`quickhybrid`支持多平台的调用，过程简述如下

- 页面中运行代码`quick.ui.alert('hello world!')`

- 在用浏览器(或微信)打开时，会判断当前环境为`H5`，于是进行API转换，转换成了`H5`下的`API命令`，浏览器执行`alert`在`H5`中的实现代码

- 在用`quick容器`打开时(比如扫一扫)，会判断当前环境为`quick`，于是进行API转换，转换成了`quick`环境下的`API命令`，命令发送到了`quick`容器，容器执行`alert`的实现代码

依靠上述的机制，实现了不同平台下的代码统一，如果进行不同平台下的移植转换时，相关代码无需改动

注，如果没有引入相应平台下的API支持库，则无法正常调用