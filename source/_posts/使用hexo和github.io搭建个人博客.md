---
title: 使用hexo和github.io遇到的问题及解决办法
date: 2018-06-13 19:35:03
tags: 总结
---

这短时间尝试使用hexo+github.io搭建炫酷的个人博客，教程网上一大把，随便找找都可以完成，这里记录几个问题

## 1. 在推送到远程分支后，出现了样式文件不加载的问题，如图

![avatar](https://chensimin0103.github.io/ChenSimin.github.io/img/res/20180613-01.png)

这个问题找了很多办法都没有解决，话说思否上的回答质量也是参差不齐。每次尝试都是失败，最后我打开了浏览器的network，查看css文件的请求过程，404没有拿到，仔细想想是请求的url地址错了呀

![avatar](https://chensimin0103.github.io/ChenSimin.github.io/img/res/20180613-02.jpg)

图中的url地址在之前是这个样子的：
``` bash
https://chensimin0103.github.io/main.0cf68a.css
```

定位到了问题，解决办法，还是百度 -_-||

在 _config.yml 里修改此处的url和root为自己项目的路径，不使用默认设置
``` javascript
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: https://chensimin0103.github.io/ChenSimin.github.io
root: /ChenSimin.github.io/
permalink: :year/:month/:day/:title/
permalink_defaults:
```
ok, 智障问题就解决了

## 2. 关于更换博客主题的方法

github上有很多炫酷或者高雅简洁的主题，可以像换皮肤一样通过配置_config.yml简单切换

首先从github上clone一个中意的主题到工程里的themes文件夹里，比如我用了yilia这个主题

然后在_config.yml里修改此处

```javascript
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: yilia
```
这样再部署时就是新的主题了，可能不同的主题还会有一些其他的功能配置，这个看着使用文档来

### 就是这样，以后想到什么还会再添加

>>>>>> 这是我写的第一篇博客 2018-6-13 陈思民

