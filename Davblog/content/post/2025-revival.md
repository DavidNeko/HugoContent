---
layout: post
title: "2025 Revival"
subtitle: "记录一次博客的复活"
description: "4年没更新的博客迎来了一次重生"
date: 2025-12-24
author:      "Daveedo"
image:       ""
tags:        ["Hugo", "Github", "Blog"]
categories:  ["Life" ]
showtoc: false
---

## 前言

距离上次更新博客已经过去了四年，这4年发生了太多事。
我记得4年前那几篇更新，也是头脑一热想着把平时学到的东西记录一下，到后面记录了5篇就再也没有更新了。 过去了1705天，我的生活也发生了巨变。

2021年4月25日，大约是我刚开始参加早大科目屡修生项目的时间点。无职，无压力，当然也无收入ww 4月末去厦门旅行、6月和A酱去南京旅行，其他的时间基本上是在逛酒吧、拍照、打游戏中度过的。充实、快乐、美好、幸福。彼时快乐青柠还没倒闭，我和A佬还没有就业压力，身体比现在充满活力，连酒量都比现在好得多。（现在我和A佬酒量都不比当年了）

到了2022年，年初长春开始封城。

我才知道，原来自由是这么珍贵。

在此刻敲下这些字的同时，死去的回忆开始慢慢复苏。我想起2022年初和老爹被封在家里的日子，除了每周一开组会以外，其他的时候都是在喝酒、打游戏。早上起床吃完饭开始打游戏，到了傍晚天暗下来开始喝酒，边喝边玩直到半夜再爬到床上开始昏睡。日复一日，我觉得自己变成了被社会软禁的游戏废人。以及被软禁是真折磨，一瓶可乐喝一个月的生活我不想再过第二次了。

到后来，大概是5月解封，6月我就跑到了日本。

于是2022年6月3日，我走上了人生的另一条轨道。

和众多留子一样，从家徒四壁的开局中，突破“没有手机卡就不能办银行账户，没有银行账户就不能找房子，没有房子地址也没法办手机卡”的多重死锁。慢慢地从民宿搬到了老式公寓，后来又搬到了新筑公寓，最后又搬到了新筑一户建。从踏上日本土地直到今天，过去了3年半，不长不短，但足以让我从一个游戏废人成长为一个独立的社畜。

最近工作状态慢慢地稳定了下来，于是我又想起了这个博客。

由于太久太久没更新，以至于完全忘记了如何更新。

...

在下面简单再次记录一下这次的博客复活过程。


## 博客复活过程

#### 前提条件
- Git Bash已经安装

### 第一步，找回“真”源码

 找到包含 `config.toml` 和 `content/` 文件夹的代码.
 
 经过一番寻找，我在Github仓库`https://github.com/DavidNeko/HugoContent/tree/master`中找到了这个Hugo博客的源代码和配置文件。

### 第二步，克隆源码仓库

``` bash
# 1. 回到存放代码的地方
cd /f/BlogRescue/

# 2. 克隆找到的源代码仓库
git clone https://github.com/DavidNeko/HugoContent.git my_blog

# 3. 进入文件夹
cd my_blog

# 4. 查看里面的文件是否包括 config.toml 和 content/ 文件夹
ls -F
```

### 第三步，安装Hugo

为了避免配置环境变量等复杂的 Windows 操作，我们要用最“土”但最有效的方法：把 Hugo 软件直接丢进这个文件夹里。

1. 下载： 去 Hugo 的官方发布页：https://github.com/gohugoio/hugo/releases
  -  向下滚动，找到 **Latest Release** (最新版本，通常是 v0.1xx.0)。
  -  点击 `Assets` 展开下载列表。
  -  找到 `hugo_extended_0.xxx.0_windows-amd64.zip` (注意要有 **extended** 字样，Windows 64位)。
  -  点击下载。

2. 解压：

-   打开下载好的压缩包。

-   里面有一个 `hugo.exe` 文件。

-   把这个 `hugo.exe` 直接解压/拖拽到刚才的 `my_blog` 文件夹里 

3. 验证： 回到 **Git Bash**，输入：

``` bash
./hugo version
```
(注意前面有个点和斜杠 ./) 如果显示类似 hugo v0.12x.x ...，说明 Hugo 准备就绪！  


### 第四步，让博客复活

现在激动人心的时刻到了，我们要尝试在本地启动博客。

在 Git Bash 里输入：

``` bash
./hugo server
```

屏幕显示 `Web Server is available at http://localhost:1313/`，去浏览器打开这个`localhost:1313`，就能看到几年前的老博客复活了！


## 重新建立博客更新逻辑

### 连接发布通道（仅需要做一次）

把目前repo下的public文件夹连接到github的`DavidNeko.github.io`仓库。

``` bash
# 1. 停止预览（如果还在跑 hugo server，按 Ctrl+C 停止它）

# 2. 删除旧的生成文件（为了防止冲突）
rm -rf public

# 3. 关键一步：把发布仓库克隆到 public 文件夹里
git clone https://github.com/DavidNeko/DavidNeko.github.io.git public
```

### 写新文章

方法 A：用命令行在 Git Bash 里输入：

``` bash
./hugo new posts/return-2025.md
```

(注意：如果你的文章目录不叫 posts，可能叫 post 或 blog，你可以去 content 文件夹里看一眼)

方法 B：手动创建

打开 Windows 文件资源管理器。

进入    `my_blog/content/posts/`。

随便复制一个旧的 `*.md` 文件，重命名，然后用记事本打开修改里面的 title（标题）和 date（日期），并写下新内容。

预览： 写完后，随时运行 `./hugo server` 在本地看看效果。

### 发布上线

1. 生成网页

``` bash
# 在 my_blog 根目录下运行
./hugo
```

(把最新的 HTML 生成到 public 文件夹里)

2. 推送网页 (更新网站)

``` bash
# 进入 public 文件夹
cd public

# 提交并推送
git add .
git commit -m "更新文章"
git push origin master

# 回到上级目录 (准备备份源码)
cd ..
```

3. 备份源码 (防止再次丢失!)

``` bash
# 现在应该回到 my_blog 目录
git add .
git commit -m "添加新文章源码"
git push origin master
```


## 本以为上面的流程会顺利，直到...

写完了文章，准备发布，结果发现在本地预览时，文章不会显示出来。而Bash上也有一段被我忽略的Warning:

> WARN found no layout file for "html" for kind "home" WARN found no layout file for "html" for kind "page"

原来是因为Git Clone默认不下载Submodule内容， 导致子模块的主题文件没有被下载下来。

于是在Git Bash里执行了下面的命令对Submodule进行拉取。

``` bash
git submodule update --init --recursive
```

拉取成功后，重新运行

``` bash
./hugo server
```

以为大功告成了，但发现了一个更大的坑。因为我使用的主题`hugo-theme-cleanwhite`是4年前的版本, 在这4年的时间里Hugo和主题都进行了更新，但我仓库中却没有进行对应的更新。导致出现了大量的报错：

例如：

> ERROR html/template:_partials/footer.html:207:12: no such template "_internal/google_analytics_async.html"

> ERROR error building site: render: [en v1.0.0 guest] failed to render pages: render of "/tags/computational-thinking" failed: "F:\BlogRescue\my_blog\Davblog\themes\hugo-theme-cleanwhite\layouts\_default\baseof.html:3:9": execute of template failed: template: taxonomy/tag.html:3:9: executing "taxonomy/tag.html" at <partial "head.html" .>: error calling partial: "F:\BlogRescue\my_blog\Davblog\themes\hugo-theme-cleanwhite\layouts\partials\head.html:18:35": execute of template failed: template: _partials/head.html:18:35: executing "_partials/head.html" at <.URL>: can't evaluate field URL in type *hugolib.pageState

> ERROR error building site: render: [en v1.0.0 guest] failed to render pages: render of "F:/BlogRescue/my_blog/Davblog/content/post/post_0007.md" failed: "F:\BlogRescue\my_blog\Davblog\themes\hugo-theme-cleanwhite\layouts\_default\single.html:24:27": execute of template failed: template: single.html:24:27: executing "header" at <partial "page_view_counter.html" .>: error calling partial: "F:\BlogRescue\my_blog\Davblog\themes\hugo-theme-cleanwhite\layouts\partials\page_view_counter.html:1:13": execute of template failed: template: _partials/page_view_counter.html:1:13: executing "_partials/page_view_counter.html" at <.URL>: can't evaluate field URL in type *hugolib.pageState
> render of "/tags/game-development" failed: "F:\BlogRescue\my_blog\Davblog\themes\hugo-theme-cleanwhite\layouts\taxonomy\tag.html:2:5": execute of template failed: template: taxonomy/tag.html:2:5: executing "main" at <partial "category.html" .>: error calling partial: "F:\BlogRescue\my_blog\Davblog\themes\hugo-theme-cleanwhite\layouts\partials\category.html:2:3": execute of template failed: template: _partials/category.html:2:3: executing "_partials/category.html" at <partial "posts.html" .>: error calling partial: "F:\BlogRescue\my_blog\Davblog\themes\hugo-theme-cleanwhite\layouts\partials\posts.html:15:11": execute of template failed: template: _partials/posts.html:15:11: executing "_partials/posts.html" at <partial "sidebar.html" .>: error calling partial: "F:\BlogRescue\my_blog\Davblog\themes\hugo-theme-cleanwhite\layouts\partials\sidebar.html:42:31": execute of template failed: template: _partials/sidebar.html:42:31: executing "_partials/sidebar.html" at <.RSSLink>: can't evaluate field RSSLink in type *hugolib.pageState

> ERROR error building site: render: [en v1.0.0 guest] failed to render pages: render of "/" failed: "F:\BlogRescue\my_blog\Davblog\themes\hugo-theme-cleanwhite\layouts\_default\list.algolia.json:6:47": execute of template failed: template: list.algolia.json:6:47: executing "list.algolia.json" at <.UniqueID>: can't evaluate field UniqueID in type page.Page

等等...

原因基本都是主题中的很多写法已经在最新版的Hugo被废弃，导致server无法正常启动。
经过一系列的修改后，删除了主题文件中不符合新版Hugo规范的代码。
后再次执行，终于成功启动了server!

## 但是...

你以为会这么顺利吗？

在启动server，打开本地测试时，发现CSS全都没被加载出来，前端完全变成了一个荒废的框架。

### 问题诊断
经排查发现，CSS 和 JavaScript 文件无法加载（返回 404 错误），原因是主题模板中的文件路径存在错误的多余前导空格。

错误示例： 代码写作 `href=" css/bootstrap.min.css"`（含前导空格） ⬇️ 浏览器实际请求路径为 `%20css/bootstrap.min.css` ⬇️ 导致 **404 Not Found**

### 修复内容
我修正了以下主题文件中的路径引用：

1. `themes/hugo-theme-cleanwhite/layouts/partials/head.html` 移除了所有 CSS 和 JS 链接属性中的前导空格。 修改对比 (Diff):

```Diff
- <link rel="stylesheet" href="{{ " css/bootstrap.min.css" | absURL }}">
+ <link rel="stylesheet" href="{{ "css/bootstrap.min.css" | absURL }}">
```

2. `themes/hugo-theme-cleanwhite/layouts/partials/sidebar.html` 移除了“精选标签 (Featured Tags)”和“RSS”链接中的前导空格。

3. `themes/hugo-theme-cleanwhite/layouts/partials/footer.html` 移除了 RSS 链接中的前导空格。

### 验证结果

视觉检查： 访问 http://localhost:1313，确认博客样式已完全恢复正常。“CleanWhite”主题的布局、字体和配色均显示正确。

控制台检查： 检查浏览器控制台 (Console)，确认样式表和脚本不再出现 404 报错。所有静态资源均加载正常。


---

## 总结

一波三折吧。

不过结果是好的，借助AI的力量也让整个过程变得事半功倍。

希望这次能尽量多更更文章，别白折腾了。