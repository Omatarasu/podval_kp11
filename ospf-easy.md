# R1 
### Initial Settings
```
interface Gi0/0/0
ip address 192.168.10.1 255.255.255.0
no shutdown 
description LAN
```
> create LAN 
```
interface Gi0/0/1
ip address 212.12.12.1 255.255.255.252
no shutdown
description WAN
```
> create WAN 

### OSPF
```
router ospf 10
router-id 1.1.1.1 (identify in ospf network)
ip ospf priority 255 (0-255, 0 - loser, 255 - DR)
passive-interface Gi0/0/0 (will not send hello packets)
network 212.12.12.0 0.0.0.3 area 0 (announcing the network)
ip ospf hello-interval 5 (same on all routers)
ip ospf dead-interval 20 (saame on all routers)
```

# R2
### Initial Settings
```
interface Gi0/0/0
ip address 192.168.20.1 255.255.255.0
no shutdown 
description LAN
```
> create LAN 
```
interface Gi0/0/1
ip address 212.12.12.2 255.255.255.252
no shutdown
description WAN
```
> create WAN 


### OSPF
```
router ospf 10
router-id 2.2.2.2 (identify in ospf network)
ip ospf priority 0 (0-255, 0 - loser, 255 - DR)
passive-interface Gi0/0/0 (will not send hello packets)
network 212.12.12.0 0.0.0.3 area 0 (announcing the network)
ip ospf hello-interval 5 (same on all routers)
ip ospf dead-interval 20 (saame on all routers)
```
