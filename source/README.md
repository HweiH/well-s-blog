## 本地调试

每次部署之前，可以使用如下方式简单调试：

1. 使用 Java 搭建本地服务器的方式；
2. 使用 Python 搭建本地简便服务器的方式：

		python -m SimpleHTTPServer 8888	// 注意：要在当前目录，然后使用 http://localhost:8888 访问

3. 使用 NodeJs 搭建本地简便服务器的方式：

		npm install anywhere -g	// 确保已经安装 anywhere 模块
		anywhere 8888			// 注意：要在当前目录，然后使用 回显的URL 访问

## 部署步骤

每次部署的步骤，可按以下三步来进行：

    hexo clean					# 清理
    hexo generate				# 衍生
    hexo deploy					# 发布

一些常用命令：

    hexo new "postName" 		# 新建文章
    hexo new page "pageName"	# 新建页面
    hexo generate 				# 生成静态页面至public目录
    hexo server 				# 开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
    hexo deploy 				# 将.deploy目录部署到GitHub
    hexo help  					# 查看帮助
    hexo version  				# 查看Hexo的版本

> well 2016年6月27日01:02:16
