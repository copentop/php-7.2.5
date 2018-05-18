### nginx 服务目录
	
	安装目录：
	/usr/local/nginx

	约定nginx服务根放置的目录，不同项目可以在根目录下创建子目录。
	/var/www/

### docker 构建命令

	docker build -t nginx_p:v1 .

	# nginx_p:v1 为 构建镜像的tag，docker run 命令依赖这个tag


### docker 启动命令

	如果本地没有web服务，可以使用端口 -p 80:80 , 如果有web服务，需要修改端口，例如 -p 8080:80 。

	本地目录和容器映射需要绝对路径，需要修改source的值

	docker run -it -d  --mount type=bind,source=F:/git/php-7.2.5/php-7.2.5/,target=/data/webpackages/php-7.2.5/ --name web_p2 nginx_p:v1 


	docker run -it -d -p 9080:80 -p 9090:443 --name web_h2 nginx-1.10.2:v1


### php
	./configure \
	--prefix=/usr/local/php7 \
	--with-config-file-path=/usr/local/php7/etc \
	--enable-fpm \
	--enable-exif \
	--enable-sockets \
	--enable-bcmath \
	--enable-mbstring \
	--enable-pcntl \
	--enable-opcache \
	--enable-zip \
	--with-fpm-user=www-data \
	--with-fpm-group=www-data \
	--with-mysqli \
	--with-pdo-mysql \
	--enable-mysqlnd \
	--with-zlib \
	--with-gd \
	--with-png-dir \
	--with-jpeg-dir \
	--with-gettext \
	--with-freetype-dir \
	--with-mcrypt \
	--with-openssl \
	--with-curl \
	--with-bz2 \
	--enable-shmop \
	--enable-calendar \
	--with-gmp  \
	--enable-sysvmsg \
    --enable-sysvsem \
    --enable-sysvshm \
	--enable-xml \
	--enable-intl \
	--with-xmlrpc 



 