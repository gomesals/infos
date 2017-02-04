```sh
$ sudo iptables -A INPUT -p tcp -m tcp --dport 8000 -j ACCEPT
$ sudo iptables -A INPUT -p tcp -m tcp --dport 8080 -j ACCEPT
$ sudo iptables -A INPUT -p tcp -m tcp --dport 5000 -j ACCEPT
$ sudo iptables -A INPUT -p tcp -m tcp --dport 3000 -j ACCEPT
$ sudo iptables -A INPUT -p tcp -m tcp --dport 35729 -j ACCEPT
```
