#network:#

    route -n
look for Flags->G

    neststat -an

 

    traceroute -n

 
    
    ifconfig
    ifconfig eth0

to change:

    vim /etc/sysconfig/network-scripts/ifcfg-eth0
    
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
