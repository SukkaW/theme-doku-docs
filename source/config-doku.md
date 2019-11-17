---
title: 「Doku」相关配置
description: 「Doku」主题的相关配置
type: docs
---

这一部分介绍的是「Doku」的 `主题配置文件`。

- `favicon`: 站点的 favicon。可选相对于「Doku」所在的根目录（`站点配置文件` 中 `url` 字段的内容）的相对路径、或包含域名的绝对路径

- `navbar`: 关于页面头部导航栏的配置
  - `logo`: 显示在导航栏中的 LOGO
  - `logo_text`: 如果你的 LOGO 中不包含文字，你可以在这里配置显示在 LOGO 边上的文字
  - `links`: 显示在导航栏的链接。在小屏移动设备上，这些链接将会显示在侧边栏中

```yaml
  links:
    zh-CN:
    # 语言名称。下述配置的链接，只会出现在以该语言显示的页面的导航栏中。
    # 目前「Doku」主题尚不支持多语言文档，这里在配置文件中预留语言以备扩展。
      - logo: 'fab fa-github'
        # 显示在链接旁边的图标，目前仅支持 font-awesome，输入 font-awesome 图标的完整名字
        # 如果不想设置图标留空即可
        text: 'GitHub'
        # 链接的文字
        url: 'https://github.com/sukkaw/hexo-theme-doku'
        # 链接的 URL，可选相对路径、或包含域名的绝对路径
      # 以上是一个链接的单位。多个链接只需重复上述配置即可。
      - logo:
        text: '更新日志'
        url: '/changelog/newest.html'
```


- `sidebar`: 侧边栏链接目录

```yaml
sidebar:
  zh-CN:
  # 语言名称。下述侧边栏配置，只会在以该语言显示的页面中生效。
    docs:
    # 页面类型名称。下述侧边栏配置，只会在这一类型的页面中显示
      level: 2 # 使用一级侧边栏（1）或二级侧边栏（2）
      items: # 配置侧边栏链接
```

```yaml
      # 以下是一个一级侧边栏的配置样例
      level: 1
      items:
        - 开始使用 | start.html # 格式为 "[链接文字] | [链接的 URL]"
        # URL 可选相对路径、或包含域名的绝对路径
        # 注意 "|" 前后都有空格
        - 配置文件 | config.html
        # 如需配置多个链接，重复配置即可
```

```yaml
      # 以下是一个二级侧边栏的配置样例
      level: 2
      items:
        - 开始使用: # 子标题
          - 安装 | install.html # 格式为 "[链接文字] | [链接的 URL]"
          - 配置 | config.html
        - 基本使用:
          - 编写 | writing.html
```

以下样例是「Doku」文档的侧边栏配置：

```yaml
sidebar:
  zh-CN: # 语言。
    docs: # 文档类型。以下配置的侧边栏内容只会在 zh-CN 语言、类型为「docs」的页面下显示
      level: 2 # 二级侧边栏
      items:
        - 开始使用: # 二级菜单栏需要包括子标题
          - '概述 | /'
          - '开始使用 | start.html'
          - '基本概念 | learn.html'
        - 配置:
          - 'Hexo 相关配置 | config-hexo.html'
          - '「Doku」相关配置 | config-doku.html'
        - 写作:
          - '写作 | writing.html'
          - '标签插件 | tag-plugins.html'
    changelog: # 另一个文档类型，以下配置的侧边栏内容只会在 zh-CN 语言、类型为「changelog」的页面下显示
      level: 1 # 一级侧边栏
      items:
        - 0.1.0 | changelog/newest.html # 一级侧边栏不包括子菜单，只包括链接
```

- `github`: GitHub 相关配置
  - `repo`: 如果你的文档开源在 GitHub，可以填写 Repo 名称 如 `sukkaw/theme-doku-docs`
  - `edit_on_github`: 当填写了 `repo` 并在这里 `enable` 后会在文档头部显示「在 GitHub 上编辑」的按钮
