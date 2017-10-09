# Полезное для Docker'а

## Запустить инстанс PostgreSQL 9.6

```
docker run\
	--name postgres\
	-e POSTGRES_PASSWORD=gfhjkm\
	-p 5432:5432\
	-v /home/gregor/Docker/postgres:/var/lib/postgresql/data\
	-d postgres:9.6
```

