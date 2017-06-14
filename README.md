# celery 在线实验环境

## 软件简介

Celery是基于分布式消息传递的开源异步任务队列/作业队列。它专注于实时操作，但也支持调度。

所属类别是服务器软件

特点:

1.易于整合

2.多代理支持

## 软件官网

http://www.celeryproject.org/

## Dockerfile 使用方法

启动一个celery worker（RabbitMQ Broker）
```
$ docker run --link some-rabbit:rabbit --name some-celery -d celery
```
检查集群的状态
```
$ docker run --link some-rabbit:rabbit --rm celery celery status
```
启动celery worker（Redis Broker）
```
$ docker run --link some-redis:redis -e CELERY_BROKER_URL=redis://redis --name some-celery -d celery
```
检查集群的状态
```
$ docker run --link some-redis:redis -e CELERY_BROKER_URL=redis://redis --rm celery celery status
```

## 资源链接

- http://www.celeryproject.org/
- http://docs.jinkan.org/docs/celery/
- https://blog.syncano.io/configuring-running-django-celery-docker-containers-pt-1/
