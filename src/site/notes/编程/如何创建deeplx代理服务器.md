---
{"dg-publish":true,"permalink":"/编程/如何创建deeplx代理服务器/","created":"","updated":""}
---


# vps-docker部署

## 准备

- 首先需要一个能访问外网(deepl服务)的服务器,比如香港服务器,假设你的服务器的ip为`111.111.111.111`
- 允许你想要的端口通过防火墙,这里设置为`8081`
- 安装docker到服务器,教程查看[[编程/如何安装docker到服务器\|如何安装docker到服务器]]

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

# okteto 容器部署

## 准备

- github账号一个
- 每24小时内存在用户使用接口,不然会清空数据

## 部署

1. github fork 项目 [OwO-Network/DeepLX: DeepL Free API (No TOKEN required) --- OwO-Network/DeepLX：DeepL 免费 API（无需 TOKEN） (github.com)](https://github.com/OwO-Network/DeepLX)![image.png](https://www.ake1.com/mkoss/2023-07-13/d79046d6.png)

2. 打开Okteto [Okteto --- 八位组](https://cloud.okteto.com/login) 使用github登录![image.png](https://www.ake1.com/mkoss/2023-07-13/1289d000.png)

3. ![image.png](https://www.ake1.com/mkoss/2023-07-13/d3c0c5b6.png)

4. ![image.png](https://www.ake1.com/mkoss/2023-07-13/09be1304.png)

5. 点击部署 ![image.png](https://www.ake1.com/mkoss/2023-07-13/46ccb24b.png)


- 接口连接为 `https://deeplx-micah123321.cloud.okteto.net/translate`
- 请根据你的名字修改3级域名