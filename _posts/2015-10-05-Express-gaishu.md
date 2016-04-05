---
layout: post
title:  "Express框架-概述"
date:   2015-11-19 23:15:32
categories: Express
---

* content
{:toc}
  
Express是目前最流行的基于Node.js的Web开发框架，可以快速地搭建一个完整功能的网站。

### **快速开发**

通过一行命令，即可生成框架基础模版，可节省很多手写代码。
下面的命令可查看express命令可使用的全部参数

    $ express -h

例如：通过下面的命令，即可生成一个express项目，并进入到项目目录。


    $ express myapp & cd myapp

	
如果你有终极管理员权限可以运行下面命令

	$ npm install -g express-generator

	
安装完成后，我们可以在终端运行


	$ express -V
	
	
查看到express当前版本，到此express安装完毕。	

使用express命令

运行 express -h 命令可得到全部参数和其说明

	-V，--version输出版本号
	-e，--ejs  添加EJS引擎的支持（默认为jade）
	-H,  --hogan 添加hogan.js引擎支持
	-c，--CSS <引擎名> 添加样式表<引擎名>的支持，支持的引擎有 less 、stylus 、compass（默认为纯CSS）
	-f， --force 如果有同名的项目目录，就会被覆盖。
	

注意参数大小写。

这里的ejs/jade/hogan.js引擎，是指动态页模版引擎。less/stylus/compass引擎，是指css模版引擎。

动态页模版引擎，之前章节已介绍过原理，这里不多说，不同的模版无非是语法不同，最终输出的都是html页面。
	
	
这时，我们会发现项目目录下多了一个 node_modules 目录，这是刚刚下载的依赖模块。

最后运行下面的命令即可运行：


    npm start

    
通过浏览器访问 localhost:3000 即可访问到页面，只要几条命令即可完成项目模版，很快捷方便。    

    
---


----------
