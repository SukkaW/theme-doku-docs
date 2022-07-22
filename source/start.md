---
title: 开始使用
description: 安装 Hexo 与「Doku」主题
type: docs
---

在使用「Doku」撰写文档之前，你需要先安装 Hexo。

[Hexo](https://hexo.io) 是一个基于 [Node.js](https://nodejs.org/) 的高效静态网站生成器（Static Site Generator）。虽然为撰写博客设计，但是可以用于如撰写文档的更多用途。通过 Hexo 你可以轻松地使用 Markdown 撰写内容，除了 Markdown 本身的语法之外，还可以使用 Hexo 提供的「标签插件」来快速的插入特定形式的内容。

## 安装 Hexo

```bash
$ npm install -g hexo-cli
```

安装 Hexo 需要 [Node.js](https://nodejs.org) 和 [Git](http://git-scm.com/)。

你可以参考 [Hexo 官方推出的安装指南](https://hexo.io/docs/) 安装 Hexo。

## 创建站点

使用 `hexo-cli` 初始化一个 Hexo 站点：

```bash
$ hexo init <folder>
$ cd <folder>
```

Hexo 初始化完成以后，注意删除 `source/_posts` 目录（及其其中的文件）。

## 下载「Doku」

### 直接下载

[下载最新 Release 版本](https://github.com/SukkaW/hexo-theme-doku/releases/latest)

> 释出的最新的稳定版本

[下载其它 Release 版本](https://github.com/SukkaW/hexo-theme-doku/releases)

> GitHub Release 页面提供所有版本

从 Release 中的「Assets」下载 `Source Code (zip)` 或 `Source Code (tar.gz)`，解压后得到的文件夹放置在 `themes` 目录下，并将文件夹重命名为 `doku`。

### 使用 Git

在 Hexo 站点目录下，执行下述命令：

```bash
cd themes
git clone https://github.com/SukkaW/hexo-theme-doku.git doku
cd doku
git checkout {branch/tags name/commit hash}
```

> 你可以自己决定想要使用的分支；使用 Git 下载「Doku」以后还可以使用 `git pull` 更新「Doku」。

## 启用「Doku」

因此，你需要把「Doku」主题目录下的 `_config.example.yml` 复制一份到站点目录并把副本重命名为 `_config.doku.yml`。接着，修改 Hexo 站点目录下的 `_config.yml` 中 `theme` 字段为 `doku` 即可。

```diff
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
-theme: landscape
+theme: doku
```

{% note warning 关于低版本 Hexo 的注意事项 %}
如果你使用的 Hexo 版本未支持自动覆盖主题配置，那么上述配置文件结构（即 `_config.doku.yml`）将不可用，你需要将 `_config.example.yml` 复制一份到主题目录（与 `_config.example.yml` 同目录）并更名为 `_config.yml` 来达到上述结构的相同效果。但站点目录下的 `theme` 字段配置是相同的，即修改为 `doku`。

注：若使用的是最新版本的 Hexo 则可以直接忽略上一段的内容。
{% endnote %}

## 运行「Doku」

在 Hexo 站点目录下运行下述命令启动一个 Hexo Server：

```bash
$ hexo s --debug
```

> 由于这是你首次运行「Doku」，建议带上 `--debug` 参数。注意观察命令行输出是否有任何异常信息，如果遇到问题，这些信息将帮助开发者更好的定位错误。

当命令行输出下述内容时说明 Hexo 已经监听在本机的 4000 端口，此时可以使用浏览器访问 http://localhost:4000 ，检查站点是否正确运行。

```
INFO  Hexo is running at http://localhost:4000/. Press Ctrl+C to stop.
```

现在，你已经成功安装并启用了「Doku」。在开始使用「Doku」撰写文档之前，我们需要先学习一些关于「Doku」的知识。
