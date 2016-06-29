# 使用Hexo框架搭建个人博客

## 步骤

1. 安装Git [?][1]

	使用 ./tools/Git/ 目录中的 Git-2.6.3-64-bit.exe 软件安装配置好Git，具体参考：
	* [如何在windows下安装GIT][2]
	* [Windows系统下Git安装图解][3]
	
2. 安装Node.js [?][4]
	
	使用 ./tools/Nodejs/ 目录中的 node-v4.4.6-x64.msi 软件安装配置好Node，具体参考：
	* [nodejs-v4.4.6-api][5]
	* [参考本地开发手册][6]
3. 申请GitHub在线账号 [?][7]
	
	[GitHub](http://github.com/)用于托管博客源码以及发布博客网站，我们也可以使用[Coding](http://coding.net/)

	> PS：可以使用[HTTPS](http://www.cnblogs.com/zhcncn/p/3731707.html)协议，但最好使用[SSH](http://blog.csdn.net/keyboardota/article/details/7603630)协议，免去每次从GitHub库中同步资源时需要输入账号密码的过程

4. 安装Hexo [?][8]
	> 使用 `npm` 命令，如果有被“墙”的情况，请使用淘宝的NPM镜像工具：`npm install -g cnpm --registry=https://registry.npm.taobao.org`  将 `npm` 命令替换成 `cnpm` 使用

	*新建个文件夹作为博客根目录，命令行下进入到该根目录，按照如下命令进行：*

		npm install -g hexo-cli	// 安装Hexo命令行工具CLI
		npm install hexo --save	// 安装Hexo博客框架
		hexo init 				// 初始化，完毕后即可
		hexo server -g			// 生成博客静态页并启动服务，http://localhost:4000 本地访问
	
	> PS: 推荐安装Hexo的Git插件：[hexo-deployer-git](http://github.com/hexojs/hexo-deployer-git)，`npm install hexo-deployer-git --save`

5. 安装Hexo相关插件 [?][9]
	
	这里给出一个*package.json*文件，内容如下：

		{
		  "name": "hexo-site",
		  "version": "0.0.0",
		  "private": true,
		  "hexo": {
		    "version": "3.2.0"
		  },
		  "dependencies": {
		    "hexo": "^3.2.0",
		    "hexo-deployer-git": "^0.2.0",
		    "hexo-generator-archive": "^0.1.4",
		    "hexo-generator-baidu-sitemap": "^0.1.1",
		    "hexo-generator-category": "^0.1.3",
		    "hexo-generator-feed": "^1.1.0",
		    "hexo-generator-index": "^0.2.0",
		    "hexo-generator-search": "^1.0.2",
		    "hexo-generator-seo-friendly-sitemap": "0.0.16",
		    "hexo-generator-sitemap": "^1.1.2",
		    "hexo-generator-tag": "^0.2.0",
		    "hexo-renderer-ejs": "^0.2.0",
		    "hexo-renderer-marked": "^0.2.10",
		    "hexo-renderer-stylus": "^0.3.1",
		    "hexo-server": "^0.2.0"
		  }
		}

	> PS：通过这个*package.json*文件可以快速搭建Hexo博客： 
	> 
	> 1）新建一个文件夹，命名为blog，作为Hexo博客根目录；
	> 
	> 2）在blog文件夹下新建*package.json*文件，将上面的内容复制粘贴进去；
	> 
	> 3）命令行进入到blog目录，执行 `npm install` 命令，等待执行完毕，Hexo博客框架即可搭建完毕；
	> 
	> 4）使用 `hexo s -g` 命令，执行完毕后访问 http://localhost:4000 即可本地访问预览；
	> 
	> **注意：能够快速搭建的前提是安装了 node.js、hexo-cli，如果不清楚，请参考_[2. 安装Node.js、4. 安装Hexo]_**

6. Hexo个性化：安装 [yelee][10] 主题 [?][11]

	* yelee主题[预览][12]
	* yelee主题[安装][13]
		* 1) 命令行进入Hexo博客框架根目录下，执行 
			
				git clone https://github.com/MOxFIVE/hexo-theme-yelee.git themes/yelee
			
			之后打开当前根目录下的 _config.yml 文件，修改为 `theme: yelee # 博客主题`并保存，当前命令行执行
				
				hexo clean		// 清除
				hexo server -g	// 生成静态博客页面并打开服务器，访问 http://localhost:4000 访问预览

		* 2) 当前目录下 ./themes/ 文件夹中，将yelee文件夹所有内容复制粘贴到你自己的Hexo博客框架根目录下themes文件夹中，之后打开你自己的Hexo博客框架根目录下的 _config.yml 文件，修改为 `theme: yelee # 博客主题`并保存，当前命令行执行
				
				hexo clean		// 清除
				hexo server -g	// 生成静态博客页面并打开服务器，访问 http://localhost:4000 访问预览

	* yelee主题[使用说明][14]

7. 参考资料

	* [http://ibruce.info/2013/11/22/hexo-your-blog/][15]
	* [http://blog.csdn.net/jzooo/article/details/46781805][16]

[1]: http://baike.baidu.com/link?url=q2K7vqCXq55cwR_wFr0Q65PprJbOdNGA7vuKbIe97lgcPctZFUN603xGb6Ilo5C8JVN9ifdsaNaHBakeEb3CrRemVFBuP-e_q4vkGVOANpK		"Git介绍"
[2]: http://jingyan.baidu.com/article/90895e0fb3495f64ed6b0b50.html																					"如何在windows下安装GIT"
[3]: http://blog.csdn.net/jiguanghoverli/article/details/7902791 																					"Windows系统下Git安装图解"
[4]: http://baike.baidu.com/link?url=dEE65i0ySZgY1l98IqotYwHstkQR61z-wJICadvqMl-8DFXhv_VuVUq_95VmAbV3JESZtutlhdYoYbotKbjg6a 							"Node.js"
[5]: https://nodejs.org/dist/v4.4.6/docs/api/ 																										"nodejs-v4.4.6-api"
[6]: ./tools/Nodejs/nodejs-v4.4.6-api/all.html 																										"参考本地开发手册"
[7]: http://baike.baidu.com/link?url=B4WsVB08In3DAAbSPEKIOEiKfz-LrIJo_g6MZavIp4aBc5Xbj0-fig70Y8iQI8VhI-jy8ppvRWmQvzT8zcm7Fa							"申请GitHub在线账号"
[8]: http://jingyan.baidu.com/article/a378c96093ef51b328283026.html																					"安装Hexo"
[9]: http://hexo.io/plugins/																														"安装Hexo相关插件"
[10]: http://github.com/MOxFIVE/hexo-theme-yelee																										"yelee"
[11]: http://hexo.io/themes/																														"Hexo个性化：安装yelee主题"
[12]: http://moxfive.xyz/																															"yelee主题预览"
[13]: http://github.com/MOxFIVE/hexo-theme-yelee																										"yelee主题安装"
[14]: http://moxfive.coding.me/yelee/																												"yelee主题使用说明"
[15]: http://ibruce.info/2013/11/22/hexo-your-blog/																									"搭建你的Hexo"
[16]: http://blog.csdn.net/jzooo/article/details/46781805																							"零基础免费搭建个人博客-hexo+github"
