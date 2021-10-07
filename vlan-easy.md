# Topology
![vlan](https://user-images.githubusercontent.com/62337797/136457864-0beed1c5-a800-460a-9b83-1cae72b8338f.png)
# SW1
```
vlan 10
name JoJo
vlan 20
name Naruto
```
> создание vlan и логичное именование 
```
interface fa0/3
switchport mode trunk
no shutdown
```
> перевод интерфейса в режим пропускания всех vlan
```
interface fa0/1
switchport mode access 
switchport access vlan 10
no shutdown
interface fa0/2
switchport mode access 
switchport access vlan 20
no shutdown
```
> раскидывание интерфейсов по vlan 

# SW2
```
vlan 10
name JoJo
vlan 20
name Naruto
```
> создание vlan и логичное именование 
```
interface fa0/3
switchport mode trunk
no shutdown
```
> перевод интерфейса в режим пропускания всех vlan
```
interface fa0/1
switchport mode access 
switchport access vlan 20
no shutdown
interface fa0/2
switchport mode access 
switchport access vlan 10
no shutdown
```
> раскидывание интерфейсов по vlan 
