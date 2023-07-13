---
{"dg-publish":true,"permalink":"/编程/如何安装docker到服务器/","created":"","updated":""}
---


# 判断环境

输入`uname -r`查看内核版本
`3.10.0-1062.18.1.el7.x86_64`

在输入 `cat /etc/os-release` 查看系统版本

```shell
NAME="CentOS Linux"
VERSION="7 (Core)"
ID="centos"
ID_LIKE="rhel fedora"
VERSION_ID="7"
PRETTY_NAME="CentOS Linux 7 (Core)"
ANSI_COLOR="0;31"
CPE_NAME="cpe:/o:centos:centos:7"
HOME_URL="https://www.centos.org/"
BUG_REPORT_URL="https://bugs.centos.org/"

CENTOS_MANTISBT_PROJECT="CentOS-7"
CENTOS_MANTISBT_PROJECT_VERSION="7"
REDHAT_SUPPORT_PRODUCT="centos"
REDHAT_SUPPORT_PRODUCT_VERSION="7"
```

这里为centos 7 64x版本

# 安装指令

- 一步一步执行

```shell

# 安装工具包
yum install -y yum-utils

#部署镜像下载地址

# 国外
yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo


#更新yum软件包索引
yum makecache fast

#最新版本安装命令 ce版本为社区版 ee为企业版
yum install docker-ce docker-ce-cli containerd.io

#可以看官方文档安装指定的docker版本

#启动docker
systemctl start docker

#开机自启动
systemctl enable docker

#使用 命令判断是否运行成功
docker version

docker run hello-world

##查看镜像
[root@micah-first ~]# docker images
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
hello-world   latest    d1165f221234   6 months ago   13.3kB


```

如果运行成功则为成功安装docker
