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
    
###ip forword:##
    cat /proc/sys/net/ipv4/ip_forward 
check if ip_forwarding is enabled, to chnage:

    vim /etc/sysctl.conf
    
###iptables###

    iptables -L -n
    
    
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
|25|SMTP Mail Server|
|53|DNS|
|80|WWW|
|110|POP3|
|443|HTTPS|
|3306|MySQL|
