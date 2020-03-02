# Полезности для PostgreSQL

## Про бэкапы

https://habr.com/ru/post/485622/

## Установка свежей версии из пакетов (ubuntu)

https://www.postgresql.org/download/linux/ubuntu/

/etc/apt/sources.list.d/pgdg.list

```
deb http://apt.postgresql.org/pub/repos/apt/ xenial-pgdg main
```

```bash
# wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
# apt-get update
```

## Поменять пароль пользователя

```
# su - postgres
$ psql
> alter role postgres password 'apassword';
> flush privileges;
```

## Присоединиться к базе

```
$ psql -h 127.0.0.1 -U postgres postgres
```

## Создать роль и базу

```
create role dbowner with login encrypted password 'gfhjkm';
create database dbname with owner=dbowner encoding='UTF8';
```

## Сделать пароль для pure-ftpd

```
CREATE EXTENSION IF NOT EXISTS pgcrypto;
SELECT encode(digest('foobarbaz'::bytea, 'sha1'), 'hex');
```

## Подключить функции uuid к БД (из-под postgres)

```sql
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
```
