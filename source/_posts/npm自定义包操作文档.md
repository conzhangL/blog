---
title: npm自定义包操作文档
date: 2020-12-25 16:28:45
tags:
categories: 技术文档
---

## 一、简介

NPM 是随同 NodeJS 一起安装的包管理工具，能解决 NodeJS 代码部署上的很多问题，常见的使用场景有以下几种：

（1）允许用户从 NPM 服务器下载别人编写的第三方包到本地使用。
（2）允许用户从 NPM 服务器下载并安装别人编写的命令行程序到本地使用。
（3）允许用户将自己编写的包或命令行程序上传到 NPM 服务器供别人使用。
本文主要介绍（3）的使用方式，自定义包的创建、发布、更新、以及撤回。

<!--more-->

## 二、操作流程

1、注册 npm 账号
npm 官网地址（http://nodejs.cn/）

2、在本地登录 npm 账号
（1）cmd 进入 windows 的控制台。
（2）执行 npm login 登录账号。

3、创建一个空文件夹，在控制台中切换到文件夹下，执行如下命令
（1）`npm init`
初始化自定义 npm 的信息，根据提示填写相关信息。完成后即可生成一个 package.json。也可以执行`npm init -y `默认配置 package.json 的信息。package.json 配置的信息如下格式：

```
{
  "name": "web-export-excel",
  "version": "1.0.1",
  "description": "前端导出excel",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [
    "web",
    "export",
    "excel"
  ],
  "dependencies": {
    "fe-export-excel": "^1.0.1",
    "lodash": "^4.17.20"
  },
  "author": "conzhang",
  "license": "ISC"
}
```

4、创建一个 index.js 文件作为包入口文件,你可以在这个文件里定义你该包的操作，如函数、工具类、组件等等。

5、可以执行` node index.js`命令来执行 index.js 的内容。

6、发布 npm 包
（1）如果没有登录 npm,请先登录 npm.
（2）登录成功后，执行` npm publish`进行包的发布.
    注意：如果发布出错，可能是以下原因之一
    （1）你没有执行 npm login 进行登录
    （2）可能你的包名重复了。

7、包的更新，只需要对本地的包文件进行你需要的修改，重新发布即可。

如上就是整个包的发布流程，案例中 web-export-excel 即为该文档的操作实例。
