---
title: "How to Use Web extra Markdown"
date: 2023-08-14
draft: false
summary: "How to Use Web extra Markdown"
tags: ["MarkDown"]
showComments : true
---
## Alert
### options: none
```
{{}}
< alert >内容< /alert >
{{      }}  {{        }}
```
{{< alert >}}
**警告！**此操作具有破坏性！
{{< /alert >}}
### options: "twitter"
```
"twitter"
```
{{< alert "twitter" >}}
Don't forget to [follow me](https://twitter.com/nunocoracao) on Twitter.
{{< /alert >}}
### options: icon,cardColor,iconColor,textColor
```
icon="fire" cardColor="#e63946" iconColor="#1d3557" textColor="#f1faee"
```
{{< alert icon="fire" cardColor="#e63946" iconColor="#1d3557" textColor="#f1faee" >}}
This is an error!
{{< /alert >}}

## 引用同级文件（或者下一级但不常用）
```
{{}}
article
link="/docs/shortcodes/"
```
{{< article link="/docs/shortcodes/" >}}

## 一个小badge
```
{{}}
< badge >
< /badge >
```
{{< badge >}}
New article!
{{< /badge >}}

## Button 它有三个可选变量 href、target 和 rel，可用于指定链接的 URL、目标和关系。
```
{{}}
button
href="#button" target="_self" 
```
{{< button href="#button" target="_self" >}}
Call to action
{{< /button >}}
##   打开Google链接
```
href="https://www.google.com/" target="_block"
```
{{< button href="https://www.google.com/" target="_block" >}}
Go to google
{{< /button >}}
## 轮播图 指定参数
只能显示现有网页文件夹下的图片
```
carousel
images="{img/7.jpg,img/3.jpg,img/4.jpg,img/5.jpg,img/6.jpg}
```
{{< carousel images="{https://cdn.pixabay.com/photo/2016/12/11/12/02/mountains-1899264_960_720.jpg,img/3.jpg,img/4.jpg,img/5.jpg,img/6.jpg}" >}}

## 轮播图 自动匹配参数
```
images="img/*"        //文件夹或url
aspectRatio="21-9"    //纵横比
interval="2500"       //时间间隔 2000代表2秒
左侧默认carousel images="img/*" aspectRatio="21-9" interval="2500"右侧默认
```

| add         | 功能                                                         |
| ----------- | ------------------------------------------------------------ |
| image       | **必填** 用于匹配图像名称的正则表达式或 URL。                |
| aspectRatio | **可选** 画廊的纵横比。`16-9` 、`21-9` 或`32-9` 。默认设置为`16-9` 。 |
| interval    | **可选** 自动滚动的时间间隔，以毫秒为单位指定。默认为`2000`（2 秒）。 |
## 轮播图示例
{{< carousel images="img/*" aspectRatio="21-9" interval="2500" >}}
## 数据处理 条形图 扇形图
```
{{}}
chart
type: 'bar',
data: {
  labels: ['Tomato', 'Blueberry', 'Banana', 'Lime', 'Orange'],
  datasets: [{
    label: '# of votes',
    data: [12, 19, 3, 5, 3],
  }]
}
offer more to use
```

### 初级图片示例
{{< chart >}}
type: 'bar',
data: {
  labels: ['Tomato', 'Blueberry', 'Banana', 'Lime', 'Orange'],
  datasets: [{
    label: '# of votes',
    data: [12, 19, 3, 5, 3],
  }]
}
{{< /chart >}}

{{< chart >}}
  type: 'bar',
  data: {
    datasets: [{
      data: [20, 10],
    }],
    labels: ['a', 'b']
  }
{{< /chart >}}


{{< chart >}}  type: 'line',
  data: {
    datasets: [{
      data: [{x: '2016-12-25', y: 20}, {x: '2016-12-26', y: 10}]
    }]
  }
{{< /chart >}}

{{< chart >}}  type: 'bar',
  data: {
    datasets: [{
      data: [{x: 'Sales', y: 20}, {x: 'Revenue', y: 10}]
    }]
  }
{{< /chart >}}

{{< chart >}}  type: 'bar',
  data: {
    datasets: [{
      data: [{id: 'Sales', nested: {value: 1500}}, {id: 'Purchases', nested: {value: 500}}]
    }]
  },
  options: {
    parsing: {
      xAxisKey: 'id',
      yAxisKey: 'nested.value'
    }
  }
{{< /chart >}}
{{< chart >}}
  type: 'doughnut',
  data: {
    datasets: [{
      data: [{id: 'Sales', nested: {value: 1500}}, {id: 'Purchases', nested: {value: 500}}]
    }]
  },
  options: {
    parsing: {
      key: 'nested.value'
    }
  }
{{< /chart >}}
{{< chart >}}
  type: 'line',
  data: {
    datasets: [{
      data: [{'data.key': 'one', 'data.value': 20}, {'data.key': 'two', 'data.value': 30}]
    }]
  },
  options: {
    parsing: {
      xAxisKey: 'data\\.key',
      yAxisKey: 'data\\.value'
    }
  }
{{< /chart >}}
{{< chart >}}
  type: 'line',
  data: {
    datasets: [{
      data: {
        January: 10,
        February: 20
      }
    }]
  }
{{< /chart >}}
### 高级图片示例
{{<keyword>}}***示例***代码{{</keyword>}}
```
<chart>
type: 'bar',
data: {
  labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
  datasets: [{
    label: 'My First Dataset',
    data: [65, 59, 80, 81, 56, 55, 40],
    backgroundColor: [
      'rgba(255, 99, 132, 0.2)',
      'rgba(255, 159, 64, 0.2)',
      'rgba(255, 205, 86, 0.2)',
      'rgba(75, 192, 192, 0.2)',
      'rgba(54, 162, 235, 0.2)',
      'rgba(153, 102, 255, 0.2)',
      'rgba(201, 203, 207, 0.2)'
    ],
    borderColor: [
      'rgb(255, 99, 132)',
      'rgb(255, 159, 64)',
      'rgb(255, 205, 86)',
      'rgb(75, 192, 192)',
      'rgb(54, 162, 235)',
      'rgb(153, 102, 255)',
      'rgb(201, 203, 207)'
    ],
    borderWidth: 1
  }]
}
```
{{< chart >}}
type: 'bar',
data: {
  labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
  datasets: [{
    label: 'My First Dataset',
    data: [65, 59, 80, 81, 56, 55, 40],
    backgroundColor: [
      'rgba(255, 99, 132, 0.2)',
      'rgba(255, 159, 64, 0.2)',
      'rgba(255, 205, 86, 0.2)',
      'rgba(75, 192, 192, 0.2)',
      'rgba(54, 162, 235, 0.2)',
      'rgba(153, 102, 255, 0.2)',
      'rgba(201, 203, 207, 0.2)'
    ],
    borderColor: [
      'rgb(255, 99, 132)',
      'rgb(255, 159, 64)',
      'rgb(255, 205, 86)',
      'rgb(75, 192, 192)',
      'rgb(54, 162, 235)',
      'rgb(153, 102, 255)',
      'rgb(201, 203, 207)'
    ],
    borderWidth: 1
  }]
}
{{< /chart >}}
```
type: 'line',
data: {
  labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
  datasets: [{
    label: 'My First Dataset',
    data: [65, 59, 80, 81, 56, 55, 40],
    tension: 0.2
  }]
}
```
<!-- prettier-ignore-start -->
{{< chart >}}
type: 'line',
data: {
  labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
  datasets: [{
    label: 'My First Dataset',
    data: [65, 59, 80, 81, 56, 55, 40],
    tension: 0.2
  }]
}
{{< /chart >}}

```
type: 'doughnut',
data: {
  labels: ['Red', 'Blue', 'Yellow'],
  datasets: [{
    label: 'My First Dataset',
    data: [300, 50, 100],
    backgroundColor: [
      'rgba(255, 99, 132, 0.7)',
      'rgba(54, 162, 235, 0.7)',
      'rgba(255, 205, 86, 0.7)'
    ],
    borderWidth: 0,
    hoverOffset: 4
  }]
}
```

{{< chart >}}
type: 'doughnut',
data: {
  labels: ['Red', 'Blue', 'Yellow'],
  datasets: [{
    label: 'My First Dataset',
    data: [300, 50, 100],
    backgroundColor: [
      'rgba(255, 99, 132, 0.7)',
      'rgba(54, 162, 235, 0.7)',
      'rgba(255, 205, 86, 0.7)'
    ],
    borderWidth: 0,
    hoverOffset: 4
  }]
}
{{< /chart >}}

## 从github上便捷引用代码 只需要url
| Parameter   | Description                        |
| ----------- | ---------------------------------- |
| `url`       | **必需的** 外部托管代码文件的 URL. |
| `type`      | 用于语法突出显示的代码类型.        |
| `startLine` | **可选** 从代码文件中导入的起始行. |
| `endLine`   | **可选** 从代码文件中导入的结束行. |
### go语言
输入代码
```
go语言
codeimporter 
url="https://raw.githubusercontent.com/nunocoracao/blowfish/main/
layouts/shortcodes/mdimporter.html" 
type="go"
```
输出代码
{{< codeimporter url="https://raw.githubusercontent.com/nunocoracao/blowfish/main/layouts/shortcodes/mdimporter.html" type="go" >}}



### toml语言
输入代码
```
codeimporter url="https://raw.githubusercontent.com/nunocoracao/
blowfish/main/config/_default/hugo.toml" 
type="toml" startLine="11" endLine="18"
```
输出代码
{{< codeimporter url="https://raw.githubusercontent.com/nunocoracao/blowfish/main/config/_default/hugo.toml" type="toml" startLine="11" endLine="18" >}}

## Codeberg Card
**Codeberg**存储库的格式为 username/repo
```
< codeberg repo="forgejo/forgejo" >
```
{{< codeberg repo="forgejo/forgejo" >}}
## figure
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

![Alt text](img/3.jpg "Image caption")


{{< figure
    src="img/3.jpg"
    alt="Abstract purple artwork"
    caption="Photo by [Jr Korpa](https://unsplash.com/@jrkorpa) on [Unsplash](https://unsplash.com/)"
    >}}

<!-- OR -->

![Abstract purple artwork](img/3.jpg "Photo by [Jr Korpa](https://unsplash.com/@jrkorpa) on [Unsplash](https://unsplash.com/)")


## Gallery one

{{< gallery >}}
  <img src="img/3.jpg" class="grid-w33" />
  <img src="img/4.jpg" class="grid-w33" />
  <img src="img/5.jpg" class="grid-w33" />
  <img src="img/6.jpg" class="grid-w33" />
  <img src="img/7.jpg" class="grid-w33" />
  <img src="img/8.jpg" class="grid-w33" />
  <img src="img/9.jpg" class="grid-w33" />
  <img src="img/10.jpg" class="grid-w33" />
  <img src="img/ice.jfif " class="grid-w33" />
{{< /gallery >}}

## Gallery two

{{< gallery >}}
  <img src="img/1.jpeg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/3.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/4.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/5.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/6.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/7.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/8.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/9.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
{{< /gallery >}}


## github 项目 something wrong
emmm本地实验的时候貌似失灵了，不知道发布之后会怎么样（没学好JavaScript，看不懂，大概感觉是用了github的api吧）


源码是这样的
```
<script>
    fetch("https://api.github.com/repos/paofan25/paofan25.github.io", {
      headers: new Headers({
        'User-agent': 'Mozilla/4.0 Custom User Agent'
      })
    })
      .then(response => response.json())
      .then(data => {
        document.getElementById('github-34d7009b09e4a521d67ae02e42d4e76b-full_name').innerHTML = data.full_name;
        document.getElementById('github-34d7009b09e4a521d67ae02e42d4e76b-description').innerHTML = data.description;
        document.getElementById('github-34d7009b09e4a521d67ae02e42d4e76b-stargazers').innerHTML = data.stargazers_count;
        document.getElementById('github-34d7009b09e4a521d67ae02e42d4e76b-forks').innerHTML = data.forks;
      })
      .catch(error => console.error(error))
</script>
```
不知道是api过时了还是怎样
{{< github repo="paofan25/paofan25.github.io" >}}

## gitlab项目 something wrong
运用你的gitlab projectID
{{< gitlab projectID="278964" >}}

## 一个图标
可以自定义图标

可以通过在项目的 `assets/icons/` 目录中提供您自己的图标来添加自定义图标。然后可以使用不带 `.svg `扩展名的 SVG 文件名在简码中引用该图标。

{{< icon "github" >}}

## 数学公式支持
众所周知，latex用的是`$$`

```
katex是
(\\
\\)
```
{{< katex >}}
\\(f(a,b,c) = (a^2+b^2+c^2)^3\\)


## 重点标记
{{< keyword >}} Super skill {{< /keyword >}}


### 同行重点标记
{{< keywordList >}}
{{< keyword icon="github" >}} Lorem ipsum dolor. {{< /keyword >}}
{{< keyword icon="code" >}} **Important** skill {{< /keyword >}}
{{< /keywordList >}}
### 重点标记中的加粗
{{< keyword >}} *Standalone* skill {{< /keyword >}}


## 一些大的字
{{< lead >}}
When life gives you lemons, make lemonade.
{{< /lead >}}

# 显示两个文章

{{< list limit=2 >}}


{{< list title="Samples" cardView=true limit=6 where="Type" value="sample" >}}

## 从右向左输入的文字
- This is an markdown list.
- Its per default a LTR direction
{{% rtl %}}
- هذه القائمة باللغة العربية
- من اليمين الى اليسار
{{% /rtl %}}

## 直接输出github下面的`readme.md`文档
---文档内容开始---
{{< mdimporter url="https://raw.githubusercontent.com/nunocoracao/nunocoracao/master/README.md" >}}
---文档内容结束---

## 简单地制作流程图 运用`mermaid`
{{< mermaid >}}
graph LR;
A[Lemons]-->B[Lemonade];
B-->C[Profit]
{{< /mermaid >}}


## 一张色卡
{{< swatches "#64748b" "#3b82f6" "#06b6d4" >}}



## 以下是一份时间轴 可以自定义 图标 和 内容



{{< timeline >}}

{{< timelineItem icon="github" header="header" badge="badge test" subheader="subheader" >}}
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus non magna ex. Donec sollicitudin ut lorem quis lobortis. Nam ac ipsum libero. Sed a ex eget ipsum tincidunt venenatis quis sed nisl. Pellentesque sed urna vel odio consequat tincidunt id ut purus. Nam sollicitudin est sed dui interdum rhoncus. 
{{< /timelineItem >}}


{{< timelineItem icon="code" header="Another Awesome Header" badge="date - present" subheader="Awesome Subheader" >}}
With html code
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
{{< /timelineItem >}}

{{< timelineItem icon="star" header="Shortcodes" badge="AWESOME" >}}
With other shortcodes
{{< gallery >}}
  <img src="img/1.jpeg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/3.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/4.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/5.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/6.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/7.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/8.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />
  <img src="img/9.jpg" class="grid-w50 md:grid-w33 xl:grid-w25" />

{{< /gallery >}}
{{< /timelineItem >}}

{{< timelineItem icon="code" header="Another Awesome Header">}}
{{< github repo="nunocoracao/blowfish" >}}
{{< /timelineItem >}}

{{< /timeline >}}


## 充满高级感的自动输出效果

{{< typeit >}}
Lorem ipsum dolor sit amet 
{{< /typeit >}}



{{< typeit 
  tag=h1
  lifeLike=true
>}}
Lorem ipsum dolor sit amet, 
consectetur adipiscing elit. 
{{< /typeit >}}



{{< typeit 
  tag=h3
  speed=50
  breakLines=false
  loop=true
>}}
Lorem ipsum dolor sit amet, 
consectetur adipiscing elit. 
{{< /typeit >}}

## 便捷的运用youtube视频
{{< youtubeLite id="SgXhGb-7QbU" label="Blowfish-tools demo" >}}

我是幽灵~看不见我~
