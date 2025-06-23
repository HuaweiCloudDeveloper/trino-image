# Trino部署指南

## ‌一、环境准备

### 一、更新系统

```bash
yum -y update  
yum -y upgrade
```

## ‌二、安装docker

#### EulerOS2.0
参考：[安装Docker](https://support.huaweicloud.com/bestpractice-hce/hce_bp_0002.html)

## ‌三、拉取镜像和创建容器

### 1.拉取镜像
```bash
docker pull trinodb/trino:latest
```
### 2.创建挂载目录

```bash
# 定义容器名称
mkdir -p /opt/trino/etc
chmod -R 755 /opt/trino/etc
```

### 3.创建容器
```bash
docker run -d \
  --name trino \
  --restart always \
  -p 8080:8080 \
  -v /opt/trino/etc:/usr/lib/trino/etc \
  trinodb/trino:latest
```