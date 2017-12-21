# JSAPI权限

在`quick`容器中，除了部分API不需要权限外，其余API都需要权限校验成功后才能调用（也就是`ready`之后）

注，`H5`下的兼容API都不需要权限

以下列出`不需要权限`的API

| JSAPI | 说明 |
| :------------- |:-------------|
| ui | ui模块的所有API |
| page | page模块的所有API |
| navigator | navigator模块的所有API |