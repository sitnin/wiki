https://ohmyz.sh/

https://github.com/ohmyzsh/ohmyzsh

https://github.com/powerline/fonts








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

## Wine

https://wiki.winehq.org/Ubuntu

http://ubuntuhandbook.org/index.php/2020/01/install-wine-5-0-stable-ubuntu-18-04-19-10/

https://tecadmin.net/install-wine-on-ubuntu/

https://habr.com/en/post/124202/

https://habr.com/en/post/124606/

winetricks

## NVME / SSD в Linux

https://unixforum.org/viewtopic.php?f=82&t=146764

$ sudo systemctl enable fstrim.timer

/etc/udev/rules.d/60-schedulers.rules

ACTION=="add|change", KERNEL=="sd[a-z]", ATTR{queue/rotational}=="0", ATTR{queue/scheduler}="noop"


/etc/sysctl.d/99-sysctl.conf

vm.swappiness=1
