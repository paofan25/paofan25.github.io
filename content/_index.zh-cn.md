---
title: "这里是 泡饭25 的网站! 👻"
description: "此页面是使用 Hugo 的 Blowfish 主题搭建的"
---

<div class="flex px-4 py-2 mb-8 text-base rounded-md bg-primary-100 dark:bg-primary-900">
  <span class="flex items-center ltr:pr-3 rtl:pl-3 text-primary-400">
    {{< icon "triangle-exclamation" >}}
  </span>
  <span class="flex items-center justify-between grow dark:text-neutral-300">
    <span class="prose dark:prose-invert"> 欢迎来到 <code id="layout">泡饭25</code> 的网站！</span>

  </span>
</div>

```node
I am just human.
```

{{< youtubeLite id="SgXhGb-7QbU" label="Blowfish-tools demo" >}}

| add         | 功能                                                         |
| ----------- | ------------------------------------------------------------ |
| image       | **必填** 用于匹配图像名称的正则表达式或 URL。                |
| aspectRatio | **可选** 画廊的纵横比。`16-9` 、`21-9` 或`32-9` 。默认设置为`16-9` 。 |
| interval    | **可选** 自动滚动的时间间隔，以毫秒为单位指定。默认为`2000`（2 秒）。 |

| Parameter   | Description                        |
| ----------- | ---------------------------------- |
| `url`       | **必需的** 外部托管代码文件的 URL. |
| `type`      | 用于语法突出显示的代码类型.        |
| `startLine` | **可选** 从代码文件中导入的起始行. |
| `endLine`   | **可选** 从代码文件中导入的结束行. |

| 参数      | 功能                                                         |
| --------- | ------------------------------------------------------------ |
| `src`     | **必填** 图像的本地路径/文件名或 URL。当提供路径和文件名时，主题将尝试使用以下查找顺序来查找图像：首先，作为与页面绑定的[页面资源](https://gohugo.io/content-management/page-resources/)；然后是 `assets/` 目录中的文件；最后是，`static/`目录中的文件。 |
| `alt`     | 图像的[替代文本描述](https://moz.com/learn/seo/alt-text)。   |
| `caption` | Markdown 格式的图像标题，将显示在图像下方。                  |
| `class`   | 应用于图像的其他 CSS 类。                                    |
| `href`    | 图像应链接到的 URL。                                         |
| `target`  | `href` URL 的目标属性。                                      |
| `nozoom`  | `nozoom=true` 会禁用图像`缩放`功能。与 `href` 结合使用十分有用。 |
| `default` | 用于恢复默认 Hugo `figure` 行为的特殊参数。只需提供`default=true`，然后使用正常的 [Hugo 简码语法](https://gohugo.io/content-management/shortcodes/#figure)。 |
