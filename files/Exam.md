<div  align="center">    
 <img src="https://github.com/TKTim/EVE/blob/master/Pics/exam.jpg" width = "70%" height = "70%" alt="01" align=center />
</div>

設定DHCP:

    R1(config)#ip dhcp pool DHCP1
    R1(dhcp-config)#network 192.168.1.0 /24
    R1(dhcp-config)#default
    R1(dhcp-config)#default-router 192.168.1.1
    R1(dhcp-config)#dns-s
    R1(dhcp-config)#dns-server 8.8.8.8

R1 :

    Router(config)#ip route 192.168.2.0 255.255.255.0 e0/0 13.1.1.2 1
    Router(config)#ip route 22.1.1.0 255.255.255.0 e0/1 12.1.1.3 10
    Router(config)#ip route 23.1.1.0 255.255.255.0 e0/0 13.1.1.2
R2 :

    Router(config)#ip route 192.168.1.0 255.255.255.0 e0/0 13.1.1.1 10
    Router(config)#ip route 12.1.1.0  255.255.255.0 e0/0 13.1.1.1
    Router(config)#ip route 22.1.1.0  255.255.255.0 e0/0 23.1.1.4

R3 :

    Router(config)#ip route 192.168.1.0 255.255.255.0 e0/1 12.1.1.1 10
    Router(config)#ip route 13.1.1.0  255.255.255.0 e0/1 12.1.1.1
    Router(config)#ip route 23.1.1.0  255.255.255.0 e0/1 22.1.1.4

R4 :

    Router(config)#ip route 192.168.2.0 255.255.255.0 e0/1 23.1.1.2 1
    Router(config)#ip route 13.1.1.0 255.255.255.0 e0/1 23.1.1.2
    Router(config)#ip route 12.1.1.0 255.255.255.0 e0/1 22.1.1.3






