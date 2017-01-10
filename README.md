##配置要求
* Docker (>1.9.1)
* Docker-compose (>1.6.0)

##容器
* volumes_www (程序源码)
* cache (redis:alpine)
* db (mysql:latest)
* php-fpm (php:7.0-fpm-alpine)
* nginx (nginx:alpine)
* composer (composer/composer:alpine)

##使用方法
下载
```
git clone https://github.com/jeeinn/docker-php-init.git
cd docker-php-init
```
构建并开启
```
docker-compose up -d
```
访问
```
http://127.0.0.1
```
关闭
```
docker-compose down
```
## 更多常用命令:
* 将所有容器停止
```
docker kill $(docker ps -q)
```
* 将所有容器停止并删除
```
docker kill $(docker ps -q) ; docker rm $(docker ps -a -q)
```
* 将所有容器停止并删除，然后清除Docker中所有已下载的镜像（慎用）
```
docker kill $(docker ps -q) ; docker rm $(docker ps -a -q) ; docker rmi $(docker images -q -a) 
```
[点此查看更多常用命令](http://dockerlux.github.io/pdf/cheat-sheet-v2.pdf?spm=5176.100239.blogcont57839.60.kfpwer&file=cheat-sheet-v2.pdf)

##文件结构
* deploy（存储持久化数据、配置文件、Dockerfile）
* www   （存储开发所使用的网站程序数据）

