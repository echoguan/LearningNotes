# HEXO: (1)基本安装与部署

## 安装前提
1. Node.js
2. Git

## 安装Hexo
#### Hexo常见命令：
	hexo g/generate	#生成静态文件  
	hexo s/server	#启动服务器，可本地预览
	hexo d/deploy	#将本地文件发布到服务器上(github/Coding)
	hexo n/new	#新建文章
	hexo h/help	#查看帮助

#### QuickStart
1. 使用`npm`安装Hexo: `npm install -g hexo`
2. 安装完成后，在你想要放置个人博客文件的目录下，执行`hexo init`
3. 安装依赖包，执行一下命令`npm install`，这样Hexo博客目录就搭好了。
4. 接下来在本地预览一下博客吧。在博客目录下执行
	```
		hexo g
		hexo s
	```
	然后就可以访问 http://localhost:4000/ ，在本地看到你的博客了。

	## 发表一篇文章
