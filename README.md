# Docker 开发环境构建

## 目的

为了用最短的时间构建出高效、简洁的开发环境。

## 包含服务

| 镜像名 | 服务名 | 端口映射 | 账号 | 说明 |
|:---- | :--- | :----- | :----- | :----- |
| ubuntu:20.04 | devcmd | `22` `80` `443` | `root`/`root` | php7 + php8 + nginx + go 及常用命令 |
| mysql:8.0 | devmysql | `3306` | `root`/`root` | |
| redis:6.2 | devredis | `6379` | `123456` | |
| 更新中 ... | | | | |

## 使用说明

### 安装 Docker

忽略，请参考[网上](https://www.runoob.com/docker/ubuntu-docker-install.html)或[官方](https://docs.docker.com/)教程

### 拉取该项目

```sh
git clone https://github.com/mesfreeman/docker-dev.git
```

### 启动服务

#### 所有服务

```sh
docker-compose up --build -d
```

#### 指定服务

```sh
docker-compose up --build -d [服务名1] [服务名2]

# 示例：
docker-compose up --build -d devmysql devredis
```

### 常用命令

```sh
# 进入容器
docker exec -it devcmd bash
docker-compose exec devcmd bash

# 开启容器服务
/usr/sbin/sshd
service nginx start
service php8.0-fpm start
service php7.4-fpm start
```