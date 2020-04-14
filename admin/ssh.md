# OpenSSH

## Чтобы формардинг портов работал

На сервере (remote) в файле /etc/ssh/sshd_config надо добавить

```
GatewayPorts yes
```

## Прокинуть локальный порт 9000 на удалённую машину на порт 3000

С элоцированным tty

```bash
ssh -L 9000:localhost:3000 user@example.com
```

Без терминала

```bash
ssh -nNT -L 9000:localhost:3000 user@example.com
```

## Прокинуть порт 9000 с удалённой машины на локальный 3000

```bash
ssh -nNT -R 9000:localhost:3000 user@example.com
```

## (когда код работает у меня, но отдаёт серверному nginx)

```bash
$ ssh -nNT -R 24000:localhost:24000 fst-03
```
