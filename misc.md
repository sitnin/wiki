# Всякое разное и полезное

## Мои сети в Selectel

80.93.179.248/29
80.93.179.249
* 80.93.179.250
* 80.93.179.251
* 80.93.179.252
* 80.93.179.253
* 80.93.179.254

82.202.243.64/29
82.202.243.65
* 82.202.243.66
* 82.202.243.67
* 82.202.243.68
* 82.202.243.69
* 82.202.243.70

```eno1      Link encap:Ethernet  HWaddr 0c:c4:7a:4e:df:54
          inet addr:80.93.179.250  Bcast:80.93.179.255  Mask:255.255.255.248
          inet6 addr: fe80::ec4:7aff:fe4e:df54/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:2863286934 errors:0 dropped:0 overruns:34 frame:0
          TX packets:1226542060 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:3374842167028 (3.3 TB)  TX bytes:190136065911 (190.1 GB)
          Memory:f7100000-f717ffff

eno1:b    Link encap:Ethernet  HWaddr 0c:c4:7a:4e:df:54
          inet addr:80.93.179.251  Bcast:80.93.179.255  Mask:255.255.255.248
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          Memory:f7100000-f717ffff

eno1:c    Link encap:Ethernet  HWaddr 0c:c4:7a:4e:df:54
          inet addr:80.93.179.252  Bcast:80.93.179.255  Mask:255.255.255.248
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          Memory:f7100000-f717ffff

eno1:d    Link encap:Ethernet  HWaddr 0c:c4:7a:4e:df:54
          inet addr:80.93.179.253  Bcast:80.93.179.255  Mask:255.255.255.248
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          Memory:f7100000-f717ffff

eno1:e    Link encap:Ethernet  HWaddr 0c:c4:7a:4e:df:54
          inet addr:80.93.179.254  Bcast:80.93.179.255  Mask:255.255.255.248
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          Memory:f7100000-f717ffff

eno1:f    Link encap:Ethernet  HWaddr 0c:c4:7a:4e:df:54
          inet addr:82.202.243.66  Bcast:82.202.243.71  Mask:255.255.255.248
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          Memory:f7100000-f717ffff

eno1:g    Link encap:Ethernet  HWaddr 0c:c4:7a:4e:df:54
          inet addr:82.202.243.67  Bcast:82.202.243.71  Mask:255.255.255.248
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          Memory:f7100000-f717ffff

eno1:h    Link encap:Ethernet  HWaddr 0c:c4:7a:4e:df:54
          inet addr:82.202.243.68  Bcast:82.202.243.71  Mask:255.255.255.248
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          Memory:f7100000-f717ffff

eno1:i    Link encap:Ethernet  HWaddr 0c:c4:7a:4e:df:54
          inet addr:82.202.243.69  Bcast:82.202.243.71  Mask:255.255.255.248
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          Memory:f7100000-f717ffff

eno1:j    Link encap:Ethernet  HWaddr 0c:c4:7a:4e:df:54
          inet addr:82.202.243.70  Bcast:82.202.243.71  Mask:255.255.255.248
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          Memory:f7100000-f717ffff
```






















## Обновить Ghost

После раскатки нового кода

```
yarn
NODE_ENV=production knex-migrator migrate
```

## Сделать MacOS High Sierra Bootable USB

```
sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/VOLUME && say Boot Installer Complete
```

## Let's Encrypt SSL cert issuing

```
certbot certonly --webroot -w /var/www/html -d productology.ru -d www.productology.ru
```

https://demo.ventureclub.ru/sa/login/facebook/


## Matching для pull/push в Git

```
git config --global push.default simple
git config --global pull.default simple
```

## Посмотреть все записи типа NS с точки зрения гугла

```
dig @8.8.8.8 domain.tld -t NS
```

## Раскатать Windows на флешку из ISO-файла

> https://www.microsoft.com/en-us/software-download/windows10ISO

### Convert Windows 10 ISO to IMG file:

```
hdiutil convert -format UDRW -o ~/path/to/Windows10.img ~/path/to/Windows10.iso
```

### Then dd to copy the img to the USB disk by ID#:

```
sudo dd if=~/Downloads/Windows10.img of=/dev/rdisk2 bs=1m
```










https://la2ha.ru/dev-seo-diy/unix/socks5-proxy-server-ubuntu










https://www.digitalocean.com/community/tutorials/openvpn-ubuntu-16-04-ru
https://openvpn.net/index.php/open-source/documentation/howto.html








