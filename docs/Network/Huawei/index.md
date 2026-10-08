# Huawei

Базовая настройка коммутаторов и маршрутизаторов Huawei на базе ОС VRP.

## Первичная настройка

### Имя устройства и доступ

```
system-view
sysname SW-01

# Консольный доступ
user-interface console 0
 authentication-mode password
 set authentication password cipher <PASSWORD>

# Telnet/SSH доступ
user-interface vty 0 4
 authentication-mode password
 set authentication password cipher <PASSWORD>
 protocol inbound ssh
quit

stelnet server enable
rsa local-key-pair create
ssh user admin authentication-type password
ssh user admin service-type stelnet
```

### VLAN

```
vlan 10
 description USERS
quit

interface GigabitEthernet0/0/1
 port link-type access
 port default vlan 10
quit

interface GigabitEthernet0/0/24
 port link-type trunk
 port trunk allow-pass vlan 10 20
quit
```

### SVI (управление)

```
interface Vlanif10
 ip address 10.10.10.2 24
quit

ip route-static 0.0.0.0 0 10.10.10.1
```

### Сохранение

```
save
```
