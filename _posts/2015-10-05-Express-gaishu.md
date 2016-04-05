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

然后，运行下面命令安装依赖模块。
    $ npm install

这时，我们会发现项目目录下多了一个 node_modules 目录，这是刚刚下载的依赖模块。

最后运行下面的命令即可运行：
    npm start
    
通过浏览器访问 localhost:3000 即可访问到页面，只要几条命令即可完成项目模版，很快捷方便。    

    
---


----------
