---
title: 基本概念
description: 使用「Doku」时需要知晓的基本概念和相关知识
type: docs
---

{% note warning %}
如果你是第一次使用 Hexo，请先通读至少两遍 [Hexo 的使用文档](https://hexo.io/docs/) 以了解 Hexo 的使用和设计细节。
{% endnote %}

## Hexo

### 配置文件

在 Hexo 中有两份主要的配置文件，其文件名都是 `_config.yml`。 其中一份位于 Hexo 站点目录下，主要包含 Hexo 本身的配置；另一份位于主题目录下，这份配置由主题提供，主要用于配置主题相关的选项。

为了描述方便，在以下说明中，将前者称为 `站点配置文件`， 后者称为 `主题配置文件` 或 `「Doku」配置文件`。

### 的独立页面

Hexo 是为编写博客设计的，因此设计了针对博客文档优化的 `post` 模型。在 `post` 模型中，每篇文章都有标签（`tags`）、分类（`categories`），文章的 URL 由站点配置文件中 `permalink` 字段控制。

这种模型并不适合用于撰写文档，因此「Doku」依赖了 Hexo 的「独立页面」。在「独立页面」中，没有标签、分类，独立页面的文件不位于 `source/_posts` 目录下，并且页面的 URL 不受站点配置文件的 `permalink` 字段控制。关于页面的 URL，接下来将会进行详细的介绍。

### URL

Hexo 的配置文件中有两个关于 URL 的配置字段，`url` 和 `root`。
如果你的 Hexo 站点运行在根目录下，如 `https://doku.skk.moe`，那么在你的站点配置文件中应该这样配置：

```yaml
url: https://doku.skk.moe # 注意结尾没有 /
root: /
```

如果你的 Hexo 站点运行在子目录下，如 `https://example.com/docs/`，那么在你的站点配置文件中应该这样配置：

```yaml
url: https://example.com/docs # 注意结尾没有 /
root: /docs/ # 注意开头有 /
```

关于这部分详细内容请参考 [Hexo 的配置文档中 URL 部分](https://hexo.io/docs/configuration#URL)。

今后在「Doku」的文档中提到的「相对链接」，都是 **相对于站点配置文件中的** `root` 的链接。如按照下述进行配置，则 `https://example.com/docs/start.html` 的相对链接就应该是 `start.html` 而不是 `/docs/start.html`。

```yaml
url: https://example.com/docs # 注意结尾没有 /
root: /docs/ # 注意开头有 /
```

### 独立页面的 URL

独立页面的 URL 不受 Hexo 站点配置文件中 `permalink` 相关字段的控制。独立页面的 URL 仅由独立页面的源文件的文件名和所在的目录、或源文件的 Front-Matter 中的 `permalink` 字段控制。以下将介绍独立页面的 URL 规则。

假设你的站点配置文件中的 URL 配置如下所示：

```yaml
url: https://theme-suka.skk.moe/docs
root: /docs/
```

- 你的关于页面的内容保存在 `about.md` 中，`about.md` 直接位于 Hexo 站点目录中 `source` 目录下，那么 Hexo 生成静态页面后，你的关于页面的 URL 就应该是 `https://theme-suka.skk.moe/docs/about.html`。
- 如果你将 `about.md` 放置与 `source/about` 目录下，那么最终的 URL 会是 `https://theme-suka.skk.moe/docs/about/about.html`。
- 如果你将关于页面的内容保存在 `source/about/index.md` 文件中，那么关于页面最终的 URL 会是 `https://theme-doku.skk.moe/docs/about/index.html`（大部分 Web 服务器均支持忽略 `index.html`，因此也可以被简化为 `https://theme-doku.skk.moe/docs/about/`）。
- 如果你在 `about.md` 文件的 Front-Matter 中添加 `permalink` 字段，那么此时不论 `about.md` 所在的位置，最终生成的 URL 将会是 `https://theme-doku.skk.moe/docs/[permalink]`，注意 `permalink` 字段也是相对于站点配置文件中的 `root` 的。

## 「Doku」

### 文档类型

「Doku」在设计时考虑到大型文档的。大型文档通常包括多种类型的大型页面如「使用文档」、「API」、「指导」、「插件」，等等。以 [Hexo 的官方文档](https://hexo.io) 为 例，Hexo 的官方文档主要包括两个主要部分[「Docs」](https://hexo.io/docs/)和[「API」](https://hexo.io/api/)，并且两个部分分别包含相关的文档、以及相应的两个目录。

因此，「Doku」提供了「文档类型」的概念。「Doku」要求每篇文章都指定文章类型，并要求在配置文件中侧边栏部分配置要求为不同的「文档类型」提供对应的侧边栏配置，以便在不同类型的文档页面中分别显示不同的侧边栏内容。

### i18n

「Doku」尚不支持 i18n 多语言文档，但有计划在未来提供支持。

-----

在大屏设备上，「Doku」的外观长这样：

```
+-----------------------------------+
| [Logo] Navbar [Links]             |
+---+------------------------+------+
| S |                        |      |
| i |                        |      |
| d |                        |      |
| e | Content                | TOC  |
| b |                        |      |
| a |                        |      |
| r |                        |      |
+---+------------------------+------+
```

在小屏设备上，「Doku」的外观长这样：

```
+----------------+
| [=] [Logo]     |
+----------------+
|                |
|                |
| Content        |
|                |
|                |
+----------------+
```

### 导航栏（Navbar）

导航栏位于头部，包含 Logo 和用户配置的链接。在小屏幕设备上，Navbar 中将不再显示链接，所有的链接都会被移动到收起的侧边栏中。

在大屏幕设备上，Navbar 不会吸附在屏幕头部；在小屏设备上 Navbar 会吸附在屏幕头部、提供展开自动收起侧边栏的按钮。

### 侧边栏（Sidebar）

侧边栏位于左侧，在小屏幕设备上自动收起。在小屏设备中控制侧边栏的按钮位于 Navbar 左侧。

侧边栏用于显示当前文档类型下的文档目录；不同的文档类型应该包含不同的文档目录。「Doku」会在侧边栏中高亮当前页面的条目。

### 页面目录（TOC）

TOC 包括当前页面文字的目录。TOC 仅在大屏幕设备上显示，在小屏设备上会被自动隐藏。

如果当前页面没有 `<h1>` `<h2>` `<h3>` 等标题，TOC 将不会显示、页面内容（Content）将会占据剩余所有宽度。

### 分页栏（Pagination）

分页栏位于页面底部、包含「上一页」和「下一页」按钮。「Doku」会自动读取侧边栏相关配置，并且根据当前页面的文档类型、URL 和侧边栏条目的顺序，自动推断出「上一页」和「下一页」分别是什么。
