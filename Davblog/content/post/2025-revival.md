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

进入 my_blog/content/posts/。

随便复制一个旧的 .md 文件，重命名，然后用记事本打开修改里面的 title（标题）和 date（日期），并写下新内容。

注意： 记得把文件头部的 draft: true 改成 draft: false，否则发布时看不见。

预览： 写完后，随时运行 ./hugo server 在本地看看效果。