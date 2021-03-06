# Topology
![hreny](https://user-images.githubusercontent.com/62337797/136944800-71a73b3a-6836-401a-bcb9-768191a6a6a9.jpeg)

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

### Static Routing
```
ip route 192.168.20.0 255.255.255.0 (remote network) 212.12.12.2 (next-hop address)
```
>  Next-Hop Static Route

##### OR
``` 
ip route 192.168.20.0 255.255.255.0 (remote network) Gi0/0/1 (outgoing interface)
```
> Directly Connected Static Route

##### OR 
```
ip route 192.168.20.0 255.255.255.0 (remote network) Gi0/0/1 (outgoing interface) 212.12.12.2 (next-hop address)
```
> Fully Specified Static Route

##### Default Route
```
ip route 0.0.0.0 0.0.0.0 Gi0/0/1 (default route) 
```
### CHECK 
```
show ip route
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

### Static Routing
```
ip route 192.168.10.0 255.255.255.0 (remote network) 212.12.12.1 (next-hop address)
```
> Next-Hop Static Route 

##### OR
``` 
ip route 192.168.10.0 255.255.255.0 (remote network) Gi0/0/1 (outgoing interface)
```
> Directly Connected Static Route

##### OR 
```
ip route 192.168.10.0 255.255.255.0 (remote network) Gi0/0/1 (outgoing interface) 212.12.12.1 (next-hop address)
```
> Fully Specified Static Route

##### Default Route
```
ip route 0.0.0.0 0.0.0.0 Gi0/0/1 (default route) 
```
### CHECK 
```
show ip route
```
