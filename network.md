#network:#

routing table

    route -n
look for Flags->G

    neststat -an

 

    traceroute -n

 
    
    ifconfig
    ifconfig eth0

check MAC etc.

to change:

    vim /etc/sysconfig/network-scripts/ifcfg-eth0

    arp -n

to check table, Address vs. MAC

show known hosts:

    cat /etc/hosts

ask DNS about ip

    host google.com
    host google.com 8.8.8.8

###ip forword:##
    cat /proc/sys/net/ipv4/ip_forward 
check if ip_forwarding is enabled, to chnage:

    vim /etc/sysctl.conf
    
###iptables###

    iptables -L -n
   
there is a differnece between `127.0.0.1` and `0.0.0.0`, if you want your port to be reachable from all your network, use `0.0.0.0`
    
----
###SSH:###
    ssh -f usr@host shutdown -h now

`-f:`no login

###SCP:###
####*IMPORTANT: scp does not ask before overwriting*####

download:

    scp usr@host:remotefolder/file ./

download:

    scp localfile usr@host:remotefolder/ 

---
###well-known ports:###
---
|port|service|
|------------|------|
|20|FTP-data|
|21|FTP|
|22|SSH|
|22|telnet|
|25|SMTP Mail Server|
|53|DNS|
|80|WWW|
|110|POP3|
|443|HTTPS|
|3306|MySQL|
|6000|Xserver|

well-known ports are typically smaller than 1024

all ports can be 1024 to 65535.

---
###curl###
---

curl post:

    curl --data "param1=value1&param2=value2" https://example.com/resource.cgi

curl get:

    curl https://example.com/resource.cgi?param1=value1&param2=value2

`-I` is to get header

`-v` is verbose on `curl` side


`302 Found`: redirect


---
###nc###
---


    nc -z localhost 9999

check port

    echo -n "123" |nc localhost 999

send to port

---
###check what is using 80 port###
---

    netstat -tulpn|grep :80


---
###openssl###
---

encryption:

    echo -n "12345678"|openssl md5
    echo -n "12345678"|openssl sha1

`-n` is important to suppress new-line
