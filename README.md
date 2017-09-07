
1. `docker-compose up scrapyd` 启动容器
2. `docker-compose exec scrapyd bash` 进入容器(相当于远程登录的服务器)，容器中安装了scrapy包，可以执行scrapy的命令行工具等，因为把项目根目录挂在到了容器的`/var/code` 所以在容器中的`/var/code`目录下的内容和项目根目录一致的。
