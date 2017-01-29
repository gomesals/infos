# OpenSSL

##### Referência

 - [Installing OpenSSL on Ubuntu Linux](http://geeksww.com/tutorials/libraries/openssl/installation/installing_openssl_on_ubuntu_linux.php)
 - [Criar](http://www.akadia.com/services/ssh_test_certificate.html)
 - [Servidor](http://nginx.org/en/docs/http/configuring_https_servers.html)
 - [Redirecionamento](https://goo.gl/CncRPR)

### Instalando
Na raiz do servidor:
```sh
$ wget http://www.openssl.org/source/{versão}.tar.gz
$ wget http://www.openssl.org/source/{versão}.tar.gz.md5
$ md5sum {versão}.tar.gz
$ cat {versão}.tar.gz.md5
$ rm {versão}.tar.gz.md5
$ tar -xvzf {versão}.tar.gz
$ cd {versão}
$ ./config --prefix=/etc/openssl --openssldir=/etc/openssl
$ make
$ make install
$ ln -s /etc/openssl/bin/openssl /usr/bin/openssl
$ openssl version
```
### Gerar chave privada
```sh
$ openssl genrsa -des3 -out server.key 1024
```
### Gerar certificado
```sh
$ openssl req -new -key server.key -out server.csr
```
### Remover autenticação
```sh
$ cp server.key server.key.org
$ openssl rsa -in server.key.org -out server.key
```
### Gerar certificado avançado
```sh
$ openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.crt
```
### Instalar no servidor
```sh
$ cp {ORIGEM}server.crt {DESTINO}ssl.crt
$ cp {ORIGEM}server.key {DESTINO}ssl.key
```
### Configurar servidor
Seguir o site do [nginx](http://nginx.org/en/docs/http/configuring_https_servers.html)

