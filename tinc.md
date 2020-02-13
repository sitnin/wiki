# VPN через TINC

В ubuntu 16.04 установлен прямо из коробки (походу).

Иллюстрация: https://www.howtoforge.com/images/how_to_set_up_express_vpn_on_the_latest_ubuntu_distros/big/tinc.png

Имя сети `netname` (?)

```bash
# apt-get install tinc
# mkdir -p /etc/tinc/netname/hosts
```

/etc/tinc/netname/tinc.conf:

```
Name = externalnyc
AddressFamily = ipv4
Interface = tun0
```

/etc/tinc/netname/hosts/externalnyc:

```
Address = externalnyc_public_IP
Subnet = 10.7.50.1/16
```

## Генерируем ключ для машины

```bash
# tincd -n netname -K4096
```

/etc/tinc/netname/tinc-up:

```
#!/bin/sh
ifconfig $INTERFACE 10.0.0.1 netmask 255.255.255.0
```

/etc/tinc/netname/tinc-down:

```
#!/bin/sh
ifconfig $INTERFACE down
```

```bash
chmod 755 /etc/tinc/netname/tinc-*
```

