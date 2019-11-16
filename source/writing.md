---
title: 开始写作
description: 使用「Doku」创建和编写文档
type: docs
lang: zh-CN
---

当你成功完成了对 Hexo 和「Doku」的配置，是时候开始使用「Doku」创建你的文档了！

## Front-Matter

如果你阅读过 Hexo 的文档，那么你一定知道 [Front-Matter](https://hexo.io/docs/front-matter) 是什么。总的来说，Front-Matter 是用来标注每个页面的信息的。这些信息会被绑定在 Hexo 的页面变量之中。

对于「Doku」来说，由于使用「Doku」创建文档要求使用独立页面，因此没有 `categories` 和 `tags` 字段。
「Doku」依赖的字段有：

| 字段名称 | 介绍 | 默认值 |
| --- | --- | --- |
| `title` | 文档的标题，会显示在文档的头部 | 无，建议 |
| `description` | 文档的说明，会显示在文档的头部 | 无，可选 |
| `type` | [文档类型](/learn.html#文档类型) | 无，建议 |
| `lang` | 文档所在的语言（未来支持 i18n 多语言文档时会有用） | 站点配置文件中 `language` 的值，建议 |
| `date` | 文档创建日期，需符合站点配置文件中配置的日期时间格式（未来支持显示文档创建和更新日期时会有用） | 系统中文件创建的日期，建议 |
| `author` | 文档的作者（未来支持显示文档作者时会有用）| 站点配置文件中 `author` 的值，可选 |

例如，你现在正在看的这篇文档的 Front-Matter 是

```yaml
---
title: 开始写作
description: 使用「Doku」创建和编写文档
type: docs
lang: zh-CN
---
```

## 修改模板（Scaffold）

你可以修改 `scaffold` 模板目录下的 `page.md` 文件，添加上述字段，以在使用 `hexo new` 命令创建文件时可以自动添加「Doku」所需的字段了。具体使用方法请参考 [Hexo 写作文档](https://hexo.io/docs/writing) 中「模板（Scaffold）」部分内容、和你 Hexo 站点目录下 `scaffold` 目录中的文件。

当然你也可以选择手动创建 markdown 文件并复制现有的 Front-Matter。

## 创建首页

由于「Doku」尚不支持自定义首页内容，因此你需要在 `source` 目录下创建 `index.md` 文件。根据 [Hexo 渲染独立页面的规则](/learn.html#独立页面的-URL)，`index.md` 内容最终会被渲染在 `index.html` 中，也就是文档的首页。以「Doku」为例，「Doku」的 [概述](/) 页面就是「Doku」的首页。
