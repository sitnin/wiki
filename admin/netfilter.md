# Прозрачное проксирование портов без подъёма реверс-прокси

- IP прокси: 139.162.163.111
- IP цели: 188.166.70.161

## Ставим ubuntu 16.04 LTS и в него пакет

```
# apt-get update && apt-get upgrade --yes
# apt-get install --yes iptables-persistent
```

## Включаем форвардинг (один раз)

```
# nano /etc/sysctl.conf
# sysctl -p
net.ipv4.ip_forward = 1
```

## Разрешаем входящие подключения на 80 и 443

```
# iptables -A FORWARD -i eth0 -p tcp --dport 80 -j ACCEPT
# iptables -A FORWARD -i eth0 -p tcp --dport 443 -j ACCEPT
```

## Форвардинг 80 и 443

```
iptables -t nat -A PREROUTING -p tcp -d 139.162.163.111 --dport 80 -j DNAT --to-destination 188.166.70.161:80
iptables -t nat -A POSTROUTING -p tcp -d 188.166.70.161 --dport 80 -j SNAT --to-source 139.162.163.111

iptables -t nat -A PREROUTING -p tcp -d 139.162.163.111 --dport 443 -j DNAT --to-destination 188.166.70.161:443
iptables -t nat -A POSTROUTING -p tcp -d 188.166.70.161 --dport 443 -j SNAT --to-source 139.162.163.111
```

## Проверяем. Если всё хорошо, сохраняем правила на всю жизнь.

```
# service netfilter-persistent save
```

> https://interface31.ru/tech_it/2010/08/ubuntu-server-nastraivaem-forvarding-portov-na-routere.html

> https://blog.it-kb.ru/2014/07/10/ubuntu-server-14-04-lts-linux-firewall-netfilter-basic-setup-witn-iptables-rules/

> https://www.8host.com/blog/forvarding-portov-cherez-shlyuz-linux-v-iptables/
