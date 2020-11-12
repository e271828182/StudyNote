---
title: 使用hexo
categories: hexo
---

### 创建仓库StudyNote，在本地初始化hexo项目并关联到github仓库

```sh
mkdir StudyNote && cd StudyNote && hexo init
git init
# 关联到远程仓库略
```

<!--more-->

### 创建仓库 shumin0.github.io，域名前缀要与github用户名一样

```yaml
deploy:
  type: git
  repo: https://github.com/shumin0/shumin0.github.io
  branch: master
```

### 项目部署到github

```sh
npm install hexo-deployer-git --save
hexo clean
hexo deploy
```

### 增加主题

```sh
git clone https://github.com/theme-next/hexo-theme-next themes/next
```

修改config.yml

```yaml
theme: next
title: 学习记录
author: shumin0
language: ch
url: https://shumin0.github.io
```

修改themes/_config.yml
切换图标地址[https://fontawesome.dashgame.com/](https://fontawesome.dashgame.com/)
[https://fa5.dashgame.com/#/图标](https://fa5.dashgame.com/#/%E5%9B%BE%E6%A0%87)
```yaml
# Schemes
# scheme: Muse
scheme: Mist
#scheme: Pisces
#scheme: Gemini
menu:
  home: / || fa fa-home
  #about: /about/ || fa fa-user
  #tags: /tags/ || fa fa-tags
  categories: /categories/ || fa fa-th
  archives: /archives/ || fa fa-archive
sidebar:
  # Sidebar Position.
  # position: left
  position: right
social:
  GitHub: https://github.com/shumin0 || fab fa-github
github_banner:
  enable: false
  permalink: https://github.com/shumin0
  title: Follow me on GitHub
footer:
  # Icon between year and copyright info.
  icon:
    # Icon name in Font Awesome. See: https://fontawesome.com/icons
    # name: fa fa-heart
    name: fa fa-user
    # If you want to animate the icon, set it to true.
    animated: false
    # Change the color of icon, using Hex Code.
    # color: "#ff0000"
   # Powered by Hexo & NexT
  powered: false
```

重新发布

```sh
hexo clean
hexo deploy
```

### 新建页面

会新建一个菜单，在themes/_config.yml的menu.categories同步添加

```sh
hexo new page categories
```

在 categories/index.md 首行添加

```markdown
---
title: categories
date: 2020-11-10 17:41:36
type: "categories"
comments: false
---
```

在文档首行添加 categories 可将文档分类

```mark
---
title: 使用hexo
categories: hexo
---
```

### 相关命令
[官方文档](https://hexo.io/docs/)
```sh
hexo generate --watch
hexo s
# layout = post page draft
# hexo new [layout] <title>
hexo new page categories
```

### 小知识

1. 标签`<!--more-->`之后的不展示（用于首页缩略视图）
2. post相当于一篇文档