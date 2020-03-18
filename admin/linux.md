https://losst.ru/ustanovka-ubuntu-18-04

https://losst.ru/ustanovka-linux-na-uefi#_Linux_UEFI

## Монтирование образа раздела как диска

sudo mount -o loop,ro,fmask=022,dmask=011,gid=1000,uid=1000 /mnt/sdb1/sda1.img /mnt/sda1

## Увеличение количества file-watcher'ов

### 1. Добавление дополнительного конфига sysctl

```bash
$ sudo nano /etc/sysctl.d/10-file-watchers.conf
```
Содержимое файла:

```
fs.inotify.max_user_watches = 100000
```
### 2. Обновление парметров системы

```bash
$ sudo sysctl --system
```

### 3. Проверка

```bash
$ sudo sysctl -q fs.inotify.max_user_watches
```
