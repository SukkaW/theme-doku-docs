---
title: 标签插件
description: 使用「标签插件」快速写出漂亮的文档
type: docs
---

## 什么是「标签插件」

「标签插件」像是一种微模板，可以在文章中快速插入特定内容。

「标签插件」的语法是：

```
{% [标签插件的名称] [可选的标签插件的参数] %}
[可选的标签插件的内容]
{% end[标签插件的名称] %}
```

Hexo 提供了大量「标签插件」，可以在文章中快速插入 jsFiddle 代码块、Gist 代码块、YouTube Iframe 播放器、Vimeo 播放器等。具体请参考 [Hexo 文档中标签插件举例](https://hexo.io/docs/tag-plugins)。

除此以外，「Doku」还提供了以下「标签插件」：

## 提示信息（note）

提示信息「标签插件」有支持两个可选参数：

- 样式。支持的样式有：
  - none（默认样式，即直接留空）
  - dark
  - primary
  - link
  - info
  - success
  - warning
  - danger
- 标题

> 如果你想使用 提示信息 的默认样式，但是又想要传入标题参数，此时 `note` 和 标题 之间需要传入 `none`。

**默认（none）样式样例**

{% note %}
这是一条普通的提示信息
{% endnote %}

**success 样式样例**

{% note success %}
这是一条可以用来标注推荐内容的提示信息
{% endnote %}

**warning 样式样例**

{% note warning %}
这是一条可以用来标注警告内容的提示信息
{% endnote %}

**danger 样式样例**

{% note danger %}
这是一条可以用来标注危险内容的提示信息
{% endnote %}

**dark 样式样例**

{% note dark %}
这是一条普通的提示信息
{% endnote %}

**primary 样式样例**

{% note primary %}
这是一条普通的提示信息
{% endnote %}

**link 样式样例**

{% note link %}
这是一条普通的提示信息
{% endnote %}

**info 样式样例**

{% note info %}
这是一条普通的提示信息
{% endnote %}

**带样式和标题样例**

{% note danger 危险！ %}
这是一条可以用来标注危险内容的提示信息
{% endnote %}

**使用默认样式的标题样例**

{% note ' ' For Windows 用户 %}
使用 Node.js 官方安装程序时务必确保 **Add to PATH** 处于勾选状态
{% endnote %}