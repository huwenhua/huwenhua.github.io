---
layout: post
title:  "编写第一个Express应用"
date:   2015-11-20 23:15:32
categories: Express
---

* content
{:toc}
  
使用express来编写一个应用 
 
安装完express之后,创建一个文件夹,使用


	express -e	命令

<img src="{{"/css/pics/express-e.png" | prepend:site.baseurl}}" >  
	
可以快速生成一个应用的骨架	

<img src="{{"/css/pics/express-ml.png" | prepend:site.baseurl}}" >  

程序目录介绍


	bin   启动程序
	public   静态网目录
	node_modules   依赖模块包
	routes    路由器处理器目录
	views   动态页目录
	app.js  主程序
	package.json   npm命令需要的描述信息


启动服务

运行 npm start 启动程序，为什么能启动呢？你可以打开package.

	"scripts": {
		"start": "node ./bin/www"
	}
	
其实是运行的 node ./bin/www this

启动程序是 bin/www，下面是对这个程序主要代码的注释说明。

	var debug = require('debug')('myapp');

	// 加载主程序
	var app = require('../app');

	// 如果不指定服务器监听端口号默认就是 3000
	app.set('port', process.env.PORT || 3000);

	//  启动程序，开始监听客户端请求。
	var server = app.listen(app.get('port'), function() {
		debug('Express server listening on port ' + server.address().port);
	});
    
	
### app.js 主程序

下面对主程序关键代码进行注释说明。

	// 创建应用程序
	var app = express();

	// 设置动态页目录
	app.set('views', path.join(__dirname, 'views'));

	// 设置动态页模版引擎
	app.set('view engine', 'jade');

	// 中间件加载，这里不多说，之后章节会详细介绍
	app.use(favicon());
	app.use(logger('dev'));
	app.use(bodyParser.json());
	app.use(bodyParser.urlencoded());
	app.use(cookieParser());

	// 指定静态页目录
	app.use(express.static(path.join(__dirname, 'public')));

	// 加载路由处理器
	app.use('/', routes);
	app.use('/users', users);

	// 如果有任何错误都会设置成 404错误
	app.use(function(req, res, next) {
		var err = new Error('Not Found');
		err.status = 404;
		next(err);
	});

	// 如果环境设置成 开发模式，那么会打印出详细的错误信息
	if (app.get('env') === 'development') {
		app.use(function(err, req, res, next) {
			res.status(err.status || 500);
			res.render('error', {
				message: err.message,
				error: err
			});
		});
	}

	// 生产模式下，不会泄漏error
	app.use(function(err, req, res, next) {
		res.status(err.status || 500);
		res.render('error', {
			message: err.message,
			error: {}  // 不会泄漏error
		});
	});


我们可以在public 目录下创建一个 test.html 文件，内容任意，然后通过 localhost:3000/test.html 即可访问到。


### 路由

routes 目录下是路由处理器。

下面对  routes/index.js  做注释说明。

	var express = require('express');

	// 创建一个路由器
	var router = express.Router();

	// 为路由器添加路由处理器，也就是为 `/` 请求路由加入处理器
	// 当有人访问时会执行这个函数。
	// req 是请求对象，res是响应对象。
	router.get('/', function(req, res) {

	// 调用响应对象的render返回给客户端一个响应结果
	// 这个响应结果是由动态页面 views/index.jade 生成的。
		res.render('index', { title: 'Express' });
	});

	module.exports = router;

	
### 模版视图

模版识图文件一般放在views文件夹下

views/index.jade 动态模版

	extends layout

	block content
	h1= title
	p Welcome to #{title}
		
				
它最终还是会生成如下的结果，并返回给请求者（浏览器）：	

	<!DOCTYPE html>
	<html>
	<head>
		<title>Express</title>
		<link rel="stylesheet" href="/stylesheets/style.css">
	</head>
	<body>
	  <h1>Express</h1>
	  <p>Welcome to Express</p>
	</body>
	</html>
	


现在对routes/index.js这个文件稍作修改
	
	
	res.render(“index”,{title:”Express”})
	
改为

	res.render(“index”,{title:”Hello”,body:”Node.js”})
	
然后修改模版

	extends layout

	block content
	h1= title
	p Welcome to #{title+body}
	
	
重启服务去访问看结果	

这是使用express简单的编写一个web应用。

具体Api去<a href="http://www.expressjs.com.cn" target="_blank">官网</a>查看  

	
---

