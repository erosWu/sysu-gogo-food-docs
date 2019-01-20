---
layout: default
title: 代码规范
author: 罗
---

# 部署说明
{:.no_toc}

* 目录
{:toc}

## 服务器架构概览

为食喵服务器需要以下软件：Nginx、MySQL Docker、NodeJS

为了方便安装、配置、运行为食喵，我们建议运营者使用 Docker 与 Dockers Compose 实现一键化的部署。

## 部署方法

容器默认绑定宿主端口 8889，需要的话，可以在 docker-compose.yml 修改

```
docker-compose up -d
```

重新构建：

```
docker-compose up -d --build
```

> `-d` 为daemon后台运行

## 配置说明

## Egg.js

`build` 配置为应用根目录，默认为 `node-web`

关键文件：

- `node-web/Dockerfile`
- `node-web/.dockerignore`：忽略了node_modules 避免添加开发环境代码到容器中浪费时间

打包其他应用时把这两个文件拷贝过去。

egg.js 默认时候通过 daemon 启动，所以 Dockerfile 的启动命令这里也直接调用了 egg-scripts start 的命令，避开了 --daemon 参数

参考文章：
[在Docker中部署Egg.js应用及Docker常用命令 | Reno's Blog](https://beautycss.net/2018/06/06/deploy-eggjs-app-with-docker/)

## Nginx

conf.d/default.conf 为nginx配置

www 默认映射 `/usr/share/nginx/html`，静态文件可以放该目录

## MySQL

密码默认是 root（在 docker-compose.yml 修改），端口3306

mysql配置的连接地址是 mysql (内部表现为改了hosts)

## docker-compose 脚本

```yaml
version: '2'
services:
    nginx:
        restart: always
        build: ./nginx/
        image: egg-nginx
        ports:
            - "8889:80"
        # 依赖关系 先跑node
        depends_on:
            - "egg-node"
        container_name: "egg-app-nginx"
    egg-node:
        restart: always
        build: ./node-web/
        image: egg-node
        ports:
            - "7001"
        container_name: "egg-app-node"
    mysql:
        image: mysql:5.7
        ports:
            - "3306"
        # 环境变量
        environment:
            # mysql密码
            - MYSQL_ROOT_PASSWORD=root
        container_name: "egg-app-mysql"
```