# Kokomi_bot_plugin 部署教程 (适配版本 V 3.2.4)

## 前言

1.Kokomi 本质是一个**插件**，并不是一个完成的bot，需要依赖nonebot2框架或者相关频道SDK实现功能

2.默认采用作者的公开数据接口，如果您有一定的编程经验且对此有兴趣，也可以找作者获取数据接口&数据库的搭建方法

3.以下教程以nonebot2加载kokomi插件为例。如果你还没有安装nonebot2，请自行搜索教程。

## 配置环境

> 开发环境的python版本 3.8.10

### 安装需要使用的python模块

插件会使用到的模块有: `pillow` , `opencv-python` , `httpx`

使用以下的命令可以查看当前python环境内已安装的包。
```
pip list
```

如果上述需要模块不存在，可以使用下面的命令安装

```
# 安装指定模块
pip install 模块名

# 安装指定模块的指定版本
pip install 模块名==指定版本号

# 卸载指定模块
pip uninstall 模块名
```

**★ 特别注意：请检查pillow的版本，不能大于等于10.0.0版本**

### 安装字体(可能需要)

windows环境应该此步骤

linux环境下需要将插件文件内的字体文件丢到系统的字体文件夹内才能加载字体

```
插件字体文件:kokomi_bot_plugin\seripts\font
系统字体文件夹:/usr/share/font
```

macOS环境未测试，不知道

## config文件配置

> config文件路径：kokomi_bot_plugin\scripts\config.py

1.将从作者那里获取到的token填入 `API_TOKEN` 中

2.根据需要选择 `PIC_TYPE` (qq群选择`base64`,kook和dc选择`file`)

3.根据平台选择对应的 `PLATFORM` (qq,kook或者discord)

## 测试插件

运行testbot.py文件

### 如果返回值为 “ok 发送图片”

说明插件正常运行，接下来运行nb2加载插件即可。

> 如果将config文件内的 `PIC_TYPE` 设置为 `file` ，就可以在temp文件夹内看到生成的图片，但是记得测试完改回去

### 如果运行结果报错

请查看nb2的窗口或者打开错误日志查看错误信息

> 错误日志文件路径：kokomi_bot_plugin\scripts\log\error.log

遇到无法解决的问题，请联系作者


