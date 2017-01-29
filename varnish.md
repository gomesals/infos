# Varnish

##### Referência
 - [Install varnish on ubuntu](https://www.varnish-cache.org/installation/ubuntu)

```sh
$ apt-get install varnish
$ nano /etc/default/varnish
```
Depois de abrir, trocar para
```sh
DAEMON_OPTS="-a :80 \
```
Salvar, e então
```sh
$ service nginx|nginx-sp restart
$ service vernish restart
```
