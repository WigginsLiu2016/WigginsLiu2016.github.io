---
title: hexo插件：Live2D 萌萌二次元
date: 2017-08-30 19:00:00
tags: [hexo]
description: 给自己的hexo加上萌萌哒的live2d
categories: hexo插件
keywords: hexo插件

---
# hexo-helper-live2d
## 插件安装
在博客主目录下执行：

```bash
npm install -save hexo-helper-live2d
```

在主题目录下 layout/layout.ejs 或 layout/_layout.swig 中的 </body> 之前添加如下代码：

ejs:
```
<%- live2d() %>
```

swig:
```
{{ live2d() }}
```
## 配置
在站点配置文件(_config.yml)中添加参数：
```
live2d:
  model: koharu
  bottom: -60
```

## 更多请参考

我的GitHub:[GitHub](https://github.com/WigginsLiu2016/hexo-helper-live2d)