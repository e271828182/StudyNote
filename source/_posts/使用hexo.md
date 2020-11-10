---
title: 使用hexo
categories: hexo
---
说明

[官方文档](https://hexo.io/docs/)

<!--more-->

1.创建仓库StudyNote

```sh
mkdir StudyNote && cd StudyNote && hexo init
git init
git remote add origin https://github.com/e271828182/StudyNote
git config user.name e271828182
git config user.email e2.718@live.com
git add .
git commit -m "init"
git push --set-upstream origin master
```

2.创建仓库 e271828182.github.io，域名前缀要与github用户名一样

```yaml
deploy:
  type: git
  repo: https://github.com/e271828182/e271828182.github.io
  branch: master
```

3.deploy

```sh
npm install hexo-deployer-git --save
hexo clean
hexo deploy
```

```sh
git clone https://github.com/theme-next/hexo-theme-next themes/next
```

config.yml

```yaml
theme: next
title: 学习记录
author: e271828182
language: ch
url: https://e271828182.github.io
```

themes/_config.yml

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
  GitHub: https://github.com/e271828182 || fab fa-github
github_banner:
  enable: false
  permalink: https://github.com/e271828182
  title: Follow me on GitHub
```

重新发布

```sh
hexo clean
hexo deploy
```

新建页面（会新建一个菜单，在themes/_config.yml的menu.categories同步添加）

```sh
hexo new page categories
# hexo new page hello-world
```

相关命令

```sh
hexo generate --watch
hexo s
```



1. 标签`<!--more-->`之后的不展示（用于首页缩略视图）
2. post相当于一篇文档