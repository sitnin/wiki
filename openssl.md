# Генерирование самоподписного SSL-сертификата

## Шаги для мака (в терминале)

    $ nano ~/openssl_with_san.conf

При этом в `~/openssl_with_san.conf` должно быть следующее:

    default_bits        = 2048
    distinguished_name  = dn
    x509_extensions     = san
    req_extensions      = san
    extensions          = san
    prompt              = no

    [ dn ]
    countryName         = RU
    stateOrProvinceName = Russia
    localityName        = Moscow
    organizationName    = Sitnin.com

    [ san ]
    subjectAltName      = DNS:*.dev, DNS:*.local

В поле `subjectAltName` нужно прописать все домены, которые будут жить на локалхосте. Позже можно будет добавить/удалить, перегенерировав сертификат.


    $ mkdir -p /usr/local/etc/nginx/ssl
    $ cd /usr/local/etc/nginx/ssl
    $ openssl req -x509 -nodes -days 3650 -subj '/CN=localhost' -newkey rsa:2048 -keyout server.key -out server.crt -config ~/openssl_with_san.conf

Затем регистрируем сертификат в Keychain (связка System):

    $ sudo security add-trusted-cert -d -r trustRoot -s basic,ssl -k /Library/Keychains/System.keychain server.crt

Если браузеры всё ещё не распознают этот сертификат как валидный, нужно зайти в Keychain и вместо умолчаний поставить вот так: https://i.imgur.com/PYgSvPD.png
