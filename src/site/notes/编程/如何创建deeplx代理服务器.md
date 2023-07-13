---
{"dg-publish":true,"permalink":"/编程/如何创建deeplx代理服务器/","created":"","updated":""}
---


# vps-docker部署

## 准备

- 首先需要一个能访问外网(deepl服务)的服务器,比如香港服务器,假设你的服务器的ip为`111.111.111.111`
- 允许你想要的端口通过防火墙,这里设置为`8081`
- 安装docker到服务器

## 部署

- 执行命令,选一个运行

```shell

# ghcr.io
docker run -itd -p 8081:1188 ghcr.io/owo-network/deeplx:latest

# dockerhub
docker run -itd -p 8081:1188 missuo/deeplx:latest

```

运行成功后显示一串容器id值

此时你专属的deeplx的api地址就为`http://111.111.111.111:8081/translate`
