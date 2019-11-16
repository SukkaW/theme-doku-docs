---
title: Hexo 相关配置
description: 「Doku」主题推荐的 Hexo 配置
type: docs
---

这一部分介绍的是 `站点配置文件`。

{% note info %}
这里只介绍和「Doku」有关的、和使用「Doku」时推荐使用的 Hexo 配置。了解更多 Hexo 配置的详细内容请阅读 [Hexo 官方的配置说明](https://hexo.io/docs/configuration)。
{% endnote %}

## 站点信息

- `title`: 标题，将会显示在浏览器的标题栏中。
- `subtitle`: 副标题。「Doku」目前暂未使用这一字段的值。
- `description`: 网站介绍。「Doku」目前暂未使用这一字段的值。
- `keywords`: 网站关键词。「Doku」目前暂未使用这一字段的值。
- `author`: 作者名称。「Doku」目前暂未使用这一字段的值。

## URL

- `permalink`:「Doku」不依赖 Hexo 的 `post` 模型，因此不会使用这一字段的值。
- `pretty_urls`:「Doku」不依赖 Hexo 的 `post` 模型，因此不会使用这一字段的值。

## 目录

- `tag_dir`:「Doku」不依赖 Hexo 的 `post` 模型，因此不会使用这一字段的值。
- `category_dir`:「Doku」不依赖 Hexo 的 `post` 模型，因此不会使用这一字段的值。
- `i18n_dir`: 默认为 `:lang`，强烈建议保留默认设置。

## 写作

- `relative_link`: 推荐设置为 `false`，默认值为 `false`
- `highlight`: 代码高亮设置
  - `auto_detect`: 自动检查代码块使用的语言，启用后将会大大降低 Hexo 的渲染速度，推荐设置为 `false`，默认值为 `false`
  - `hljs`: 为渲染后的代码块的 CSS 类添加 `hljs-` 前缀。这是一个 Hexo 3.5.0 版本起引进的一个特性、用于适配新版 `highlight.js` 主题。「Doku」使用了 。9.16.0 版的 `highlight.js` 主题，因此需要设置为 `enable`。

## 日期/时间 格式

- `use_date_for_updated`: 当 Hexo 的「Front-Matter」中没有指定 `updated` 字段时，`page.updated` 将使用 `page.date` 的值。推荐设置为 `true`。

## 扩展

- `theme`: 设置为 `doku`。
- `meta_generator`: 在每个页面的 `<head>` 中插入 `<meta name="generator" name="Hexo [version]">`。「Doku」主题已经添加这一标签，因此可以禁用这一选项。

