<a href="https://github.com/lh1me/hexo-theme-aomori/releases">
  <img src="https://github.com/lh1me/hexo-theme-aomori/workflows/Action/badge.svg" alt="Action" />
</a>
<a href="https://github.com/lh1me/hexo-theme-aomori/releases">
  <img src="https://img.shields.io/github/release/lh1me/hexo-theme-aomori.svg" alt="Release" />
</a>
<a href="https://github.com/lh1me/hexo-theme-aomori/blob/master/LICENSE">
  <img src="https://img.shields.io/github/license/lh1me/hexo-theme-aomori.svg" alt="license" />
</a>
<br/><br/>

![image](https://raw.githubusercontent.com/lh1me/hexo-theme-aomori/master/docs/cover.jpg)

# Aomori

一款外表简约但内心华丽的 Hexo 主题。

（想到什么功能就做什么，更新完全看心情。欢迎 PR

[ENGLISH](/README.md) | [CHANGELOG](/CHANGELOG.md)

## Demo

[https://linhong.me](https://linhong.me)


## 安装主题

将 [下载](https://github.com/lh1me/hexo-theme-aomori/releases) 的 ZIP 包解压放置到 Hexo 主题目录下即可

## 开始使用

基本使用配置，需要在全局 `_config.yml` 进行以下设置

1. 启用主题

```
theme: hexo-theme-aomori
```

2. 关闭 Hexo 默认 Highlight 代码高亮

```
highlight:
  enable: false
```

---

## 主题可选功能

主题可选配置，需要在全局 `_config.yml` 进行以下设置

#### 头像

``` yml
aomori_logo: /images/avatar.jpg
```

#### 站点标题打字动画

``` yml
aomori_logo_typed_animated: true
```

#### 头部菜单

``` yml
aomori_menu:
  Home: /
  Archives: /archives
```

#### 侧边栏菜单

``` yml
aomori_widgets:
  - toc # 文章导航
  - category  #文章分类
  - tag # 文章标签
  - recent_posts  # 最新文章
  - archive #文章归档
```

#### 知识共享使用许可

``` yml
aomori_copyright: true # or false
```

#### 社交媒体

`icon` 填入 [Boxicons](https://boxicons.com/) Icon Name

`url` 链接地址

``` yml
aomori_social:
  -
    icon:
    type:
    url:
  -
    icon:
    type:
    url:
```

#### 百度链接提交

``` yml
aomori_baidu_sitepush: true  # or false
```

#### 百度统计

``` yml
aomori_baidu_analytics: ''
```

#### Google 统计

``` yml
aomori_google_analytics: 'UA-XXXXX-X'
```

#### 不蒜子 统计

由 [不蒜子](https://busuanzi.ibruce.info/) 提供的计数服务

``` yml
aomori_busuanzi: true
```

---

## 文章可选功能

配置文件：文章 Front-matter

#### 封面图片

使用 `相对路径`，参照 [资源文件夹](https://hexo.io/zh-cn/docs/asset-folders)

``` yml
cover: xxx.jpg
```

#### 封面视频

使用 `完整链接`，便于使用 CDN

每篇文章只能有一个封面视频，并且封面图片和封面视频只能同时存在其中一个

``` yml
video:
  src: src # 完整视频链接
  poster: poster # 完整视频封面图链接
```

#### 文字头部图片

可配多张，使用 `相对路径 `，参照 [资源文件夹](https://hexo.io/zh-cn/docs/asset-folders)

``` yml
photos:
- xxx.jpg
- xxx.jpg
```

#### 转载链接

可配多条

`url` 跳转链接 / `title` 显示标题

``` yml
link_reprint:
  -
    url: url
    title: title
  -
    url: url
    title: title
```

#### 参考链接

可配多条

`url` 跳转链接 / `title` 显示标题

``` yml
link_refer:
  -
    url: url
    title: title
  -
    url: url
    title: title
```

#### 置顶

在 Hexo 目录下安装依赖

```
npm i hexo-generator-index -S
```

在文章 Front-matter 增加选项

```
sticky: 100
```

更多使用方法 [点击查看](https://github.com/hexojs/hexo-generator-index)

---

## 文章可选风格

配置文件：文章头部

#### Tweet

``` yml
layout: tweet
```

---

## 文章评论

配置文件：全站 `_config.yml`

#### Disqus

填入 Disqus ID

``` yml
aomori_disqus_shortname: ''
```

#### Gitalk

``` yml
aomori_gitalk:
  enable: true
  clientID: GitHub Application Client ID
  clientSecret: GitHub Application Client Secret
  repo: GitHub repo
  owner: GitHub repo owner
  admin: 
    - GitHub repo owner and collaborators
    - GitHub repo owner and collaborators
  distractionFreeMode: true // Facebook-like distraction free mode
```

---

## 页面

#### 友情链接

1. 首先创建页面

```
hexo new page friends
```

2. 前往 `source/friends/index.md` 文件，设置 Front-matter

```
title: 友情链接 # 文章标题
layout: friends
comment: true # 是否需要评论 true: 是 false: 否
```

3. 创建数据，参照 [数据文件夹](https://hexo.io/zh-cn/docs/data-files)

4. 创建 `source/_data/friends.json`，格式如下

```
[
  {
    "name": "test1",
    "url": "https://linhong.me"
  },
  {
    "name": "test2",
    "url": "https://linhong.me"
  }
  ...
]
```

---

## 搜索

#### Algolia

1. 注册 [Algolia](https://www.algolia.com/) 账号，并创建 Index

2. 安装 [hexo-algolia](https://github.com/oncletom/hexo-algolia)

```
npm install --save hexo-algolia
```

3. 在站点 `_config.yml` 填入 Algolia 配置

```
algolia:
    applicationID: 'applicationID'
    apiKey: 'apiKey' # Search-Only API Key
    indexName: '...'
```

配置在 Algolia > API Keys 可以找到

4. 运行下面的命令更新数据

```
$ export HEXO_ALGOLIA_INDEXING_KEY=Admin API Key # Use Git Bash
# set HEXO_ALGOLIA_INDEXING_KEY=Admin API Key # Use Windows command line
$ hexo clean
$ hexo algolia
```

注意，以后发新文章后都需要运行 `hexo algolia` 更新搜索数据

4. 在站点 `_config.yml` 打开搜索功能

```
aomori_search_algolia: true
```

Enjoy.

---

# Copyright & License

Copyright (c) 2020 LIN HONG - Released under the [MIT license](LICENSE).