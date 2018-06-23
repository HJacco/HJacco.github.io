---
layout: post
title: 通过jekyll + github搭建自己的博客
category: tech
tags: [other]
---

# 通过jekyll + github搭建自己的博客

## 简介
[jekyll](https://www.jekyll.com.cn/docs/home/ "jekyll")是一款博客网站静态站点生成器，你只需要将要发布的文章以特定的格式写成markdown文件，并将最终的markdown放在jekyll下的特定目录，jekyll会自动将博客内容嵌入到一套已有的静态页面模板里，形成可发布的静态网站；jekyll可以运行在github page上，所以我们可以通过github搭建免费的可公网访问的私人博客。

## 准备
1、github账号

2、安装git

## 尝鲜式搭建
#### 1、github上新建代码仓库，注意，仓库名称必须是 `${你github的用户名}.github.io`
#### 2、在[jekyll官方主题网站]('http://jekyllthemes.org/')上找到自己喜欢的主题样式,并下载到本地
#### 3、主题根目录下的_config.yml是全局配置文件，修改Set settings下的一些信息，之后将所有的文件提交到步骤一创建的远程代码库，就可以通过浏览器访问博客了，http://${你github的用户名}.github.io

## 使用
### 目录结构
* `_config.yml` 配置文件,配置jekyll的一切以及变量
* `index.md/html` 主页文件,必须的
* `_layout` 模板文件夹,用来生成相应子页面的模板,在子页面中 layout: page 指定
* `_post` 相应子页面(博客)所在位置,文件名规则:2015-07-24-name.md/html
* `_includes` 用来包含一些常用需要的结构块文件,例如comment.使用 \{\% include file.ext \%\} 来包含(\去掉).非必须.
* `_site` 如果使用jekyll本地版生成页面就会有该文件夹.一般会被判断为不上传到github.非必须.

### 配置文件
&emsp;&emsp;配置文件保存了jekyll项目的变量配置，详细信息科参考官网[关于配置项]('http://jekyllcn.com/docs/configuration/')的介绍

### 撰写博客
&emsp;&emsp;在`_post`目录下（或者该目录下的其他子目录）新建一个markdown文件，**命名格式：`yyyy-mm-dd-标题.markdown`**,所有的博客文章必须以YAML头信息开头
	
	---
	layout: post
	title: Blogging Like a Hacker
	category: tech
	tags: [java,css,html]
	---
在头信息里可以设置预定义的变量，也可以添加自定义变量，在任意的模板里面都可以通过Liquid标签访问这些变量，例如 `{{page.tags}}`可以访问页面的tags属性

* layout 指定页面布局模板，模板在`_layouts`目录下
* permalink 指定访问该页面的最终的url
* tags 文章的分类，可以有多个标签，site.tags.${tagName}可以访问到带有tagName标签的所有文章

### 页面
&emsp;&emsp;jekyll项目根目录必须包含主页`index.html`,站点上任何 HTML 文件，包括主页，都可以使用 layout 和 include 中的内容作为公用的内容，如页面的 header 和 footer. 将合适的部分抽出放到布局中。

* 通过markdown文件的yaml头的layout属性引用layout目录下的文件
* 通过liquid标签 `\{\% include xx.html \%\}(去掉\)`引用include下的文件

