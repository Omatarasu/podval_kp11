# Topology
![ssh](https://user-images.githubusercontent.com/62337797/136414989-980b1a0a-1407-410a-b848-3220e9c95e3a.png)
# Cisco ssh configuration

```
hostname R1
```
> задаем hostname
```
ip domain-name podval.kp11
```
> задаем доменное имя
```
interface vlan 1 
ip address 10.0.10.1 255.255.255.0
no shutdown
```
> задаем адрес на SVI коммутатора
```
crypto key generate rsa
```
> генерируем пару ключей для ssh 

> необходимо выбрать длинну ключа (1024-4096 шаг 512)
```
ip ssh version 2
```
> включаем ssh второй версии
```
username master privilege 15 secret MyPA$$w0rd
```
> создаем пользователя с админскими привилегиями 
```
line vty 0 15 
login local 
transport input ssh 
```
> настраиваем все vty с 0 по 15 

> включаем авторизацию по локальной базе данных пользователей

> включаем  ssh 
