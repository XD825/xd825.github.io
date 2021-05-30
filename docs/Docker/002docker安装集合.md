# docker安装集合
## Docker安装RabbitMQ

### 下载Docker镜像

```bash
# 下载自带管理的镜像
docker pull rabbitmq:management
```

### 启动rabbitmq容器

```bash
docker run -d --hostname desire-rabbit --name desire-rabbit -e RABBITMQ_DEFAULT_USER=user -e RABBITMQ_DEFAULT_PASS=password -p 15672:15672 -p 5672:5672 rabbitmq:management
```

- `RABBITMQ_DEFAULT_USER` 设置登录用户
- `RABBITMQ_DEFAULT_PASS` 设置登录密码
- `-p 15672:15672` 映射15672端口，用来访问管理后台
- `-p 5672:5672` 映射5672端口，用来连接操作rabbit

### 访问管理后台

```bash
http://ip:15672
```