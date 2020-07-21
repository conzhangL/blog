---
title: hexo部署到github Page
date: 2020-07-21 16:47:14
categories: 技术文档
---

## 一、简介

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 [Markdown](http://daringfireball.net/projects/markdown/)（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。这里主要介绍hexo个人博客在githubPage的部署。

<!--more-->

## 二、操作步骤

1、注册自己的github账号。

2、创建仓库，仓库名称为：username.github.io。username即为你github的账号名称。

3、在本地的hexo目录下安装hexo-deployer-git插件

```
npm install hexo-deployer-git --save
```

4、修改站点配置信息，打开站点下的`_config,yml`文件，添加`deploy`信息

```
deploy:
    type: git
    repo: https://github.com/username/username.github.io
    branch: master
```

username改为你的GithHub用户名

5、部署

```
hexo cl     //清理缓存
hexo g      //生成静态文件
hexo d      //部署网站到创建的仓库
```

经过如上几步，你的个人hexo博客已部署完成。

## 最后

部署成功后，就可以使用Github提供的那个地址来访问博客了。

如我的hexo地址：https://conzhangl.github.io/

~~easy。如果该内容对你有帮助，也请分享给你的朋友吧！