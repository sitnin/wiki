# Полезное для Docker'а

## Полезная документация

Тома сильно изменились с Docker 17.06: https://docs.docker.com/storage/volumes/

https://habr.com/ru/company/flant/blog/336654/

## Показать внутрейнний адрес докер-хоста

```bash
$ ip addr show docker0 | grep -Po 'inet \K[\d.]+'
```

## Удаление всех остановленных контейнеров

```bash
$ docker container prune
```

## Запустить инстанс PostgreSQL

```
docker volume create pgdata
```

```
docker run -d
    --name postgres12
    --restart unless-stopped
    -e POSTGRES_PASSWORD=gfhjkm
    -p 127.0.0.1:5437:5432
    -v /root/docker/postgres12:/var/lib/postgresql/data
    postgres:12
```

```
docker run -d
    --name mariadb
    --restart unless-stopped
    -e MYSQL_ROOT_PASSWORD=gfhjkm
    -e MYSQL_ALLOW_EMPTY_PASSWORD=false
    -p 127.0.0.1:3306:3306
    -v root/docker/mariadb:/var/lib/mysql
    mariadb
```

```
docker exec mariadb sh -c
    'exec mysqldump --all-databases -uroot -pNy2XVuyjhnQyWhUf9PzDPN'
    > mariadb_all.sql
```

```
docker run -d
    --name mongo
    --restart unless-stopped
    -p 127.0.0.1:27017:27017
    -v /root/docker/mongo4:/data/db
    mongo:4
```

```
docker run -d
    --name mongo-express
    --restart unless-stopped
    --link mongo
    -p 127.0.0.1:27081:8081
    mongo-express
```

```
docker run -d
    --name redis
    --restart unless-stopped
    -p 127.0.0.1:6379:6379
    -v /root/docker/redis5:/data
    -d redis:5
```


```
docker run -d
    --name redis-commander
    --restart unless-stopped
    --env REDIS_HOSTS=redis
    --link redis
    -p 127.0.0.1:26379:8081
    rediscommander/redis-commander:latest
```




```
docker run -d
    --name mailhog
    --restart unless-stopped
    -p 127.0.0.1:1025:1025
    -p 127.0.0.1:8025:8025
    mailhog/mailhog
```

```
docker run -d
    --name rabbitmq
    --restart unless-stopped
    -p 127.0.0.1:5671-5672:5671-5672
    -p 127.0.0.1:15671:15671
    -p 127.0.0.1:25672:25672
    -p 127.0.0.1:4369:4369
    -p 127.0.0.1:15672:15672
    rabbitmq:3-management
```

```
docker run -d
    --name nats
    --restart unless-stopped
    -p 127.0.0.1:4222:4222
    -p 127.0.0.1:6222:6222
    -p 127.0.0.1:8222:8222
    nats
```

```
docker pull darthsim/imgproxy:latest

docker run -d
    --name ekuine_imgproxy
    --restart unless-stopped
    -e IMGPROXY_KEY=edf79ae158ae6290d790a3aa0afaca56
    -e IMGPROXY_SALT=db99a00a1e677bd458a8c93aababe5be
    -e IMGPROXY_CACHE_CONTROL_PASSTHROUGH=true
    -e IMGPROXY_USE_ETAG=true
    -e IMGPROXY_WATERMARK_URL="https://ekuine.ru/img/logo-wide-2200x580.png"
    -p 127.0.0.1:7700:8080
    darthsim/imgproxy

    -e IMGPROXY_LOG_FORMAT=pretty
    -e IMGPROXY_LOG_LEVEL=debug
```
