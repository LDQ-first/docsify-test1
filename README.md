# docsify-test1


[docsify](https://docsify.js.org/#/zh-cn/)



## 快速开始

推荐全局安装 docsify-cli 工具，可以方便地创建及在本地预览生成的文档。

```js
npm i docsify-cli -g
```

## 初始化项目

如果想在项目的 ./docs 目录里写文档，直接通过 init 初始化项目。

```js
docsify init ./docs
```


## 开始写文档

初始化成功后，可以看到 . 目录下创建的几个文件


- index.html 入口文件
- README.md 会做为主页内容渲染
- .nojekyll 用于阻止 GitHub Pages 忽略掉下划线开头的文件


直接编辑 docs/README.md 就能更新文档内容，当然也可以添加[更多页面](https://docsify.js.org/#/zh-cn/more-pages)。


## 本地预览

通过运行 docsify serve 启动一个本地服务器，可以方便地实时预览效果。默认访问地址 http://localhost:3000 。

```js
docsify serve 
```


更多命令行工具用法，参考 [docsify-cli 文档]([docsify-cli 文档](https://github.com/docsifyjs/docsify-cli))。




## 定制侧边栏

为了获得侧边栏，您需要创建自己的_sidebar.md，你也可以自定义加载的文件名。默认情况下侧边栏会通过 Markdown 文件自动生成，效果如当前的文档的侧边栏。

首先配置 loadSidebar 选项，具体配置规则见配置项#loadSidebar。

```html
<!-- index.html -->

<script>
  window.$docsify = {
    loadSidebar: true
  }
</script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
```

接着创建 _sidebar.md 文件，内容如下

```js
<!-- docs/_sidebar.md -->

* [首页](zh-cn/)
* [指南](zh-cn/guide)
```

需要在 ./docs 目录创建 .nojekyll 命名的空文件，阻止 GitHub Pages 忽略命名是下划线开头的文件。



## 用侧边栏中选定的条目名称作为页面标题

一个页面的 title 标签是由侧边栏中选中条目的名称所生成的。为了更好的 SEO ，你可以在文件名后面指定页面标题。

```js
<!-- docs/_sidebar.md -->
* [Home](/)
* [Guide](guide.md "The greatest guide in the world")
```


## 显示目录

自定义侧边栏同时也可以开启目录功能。设置 subMaxLevel 配置项，具体介绍见 [配置项#sub-max-level](https://docsify.js.org/#/zh-cn/configuration?id=sub-max-level)。

```html
<!-- index.html -->

<script>
  window.$docsify = {
    loadSidebar: true,
    subMaxLevel: 2
  }
</script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
```


## 忽略副标题

当设置了 subMaxLevel 时，默认情况下每个标题都会自动添加到目录中。如果你想忽略特定的标题，可以给它添加 {docsify-ignore} 。

# Getting Started

## Header {docsify-ignore}

该标题不会出现在侧边栏的目录中。


要忽略特定页面上的所有标题，你可以在页面的第一个标题上使用 {docsify-ignore-all} 。

# 入门 {docsify-ignore-all}

## 标题

该标题不会出现在侧边栏的目录中。

在使用时， {docsify-ignore} 和 {docsify-ignore-all} 都不会在页面上呈现。





























