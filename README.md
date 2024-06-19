apt-get install frr -y  
systemctl enable --now frr  
vim /etc/frr/daemons  
systemctl restart frr  
vtysh  
conf t  
router ospf  
passive-interface default  
network 192.168.0.0/30 area 0  
network 172.16.1.0/26 area 0  
int tun1  
no ip ospf network broadcast  
no ip ospf passive  
ipv6 ospf6 area 0  
int enp0s8  
ipv6 ospf6 area 0  
router ospf6  
ospf6 router-id 1.1.1.1  
Почему выбран OSPF? Потому что данный протокол позволяет разделять сеть на логические области, каждая из которых может иметь личную таблицу маршрутизации, что хорошо для масштабируемых сетей, так как это уменьшает нагрузку на маршрутизаторы и улучшает производительность.  
curl -L -o C:\iperf3.jpg "https://clck.ru/3BNDj5"  
Скорость отправки и приема данных - 2.22 Гбит/с  
За 10 секунд было передано 2.58 Гбит данных  
curl -L -o C:\iperf3.jpg "https://clck.ru/3BNTUA"  
apt-get install proxmox-backup-{server,client} -y  
systemctl enable --now proxmox-backup-proxy.service и все остальные  
apt-get install kernel-modules-zfs-std-def -y  
modprobe zfs  
vim /etc/modules-load.d/zfs.conf  
прописать на всех роутерах порт 8007  
настроить proxmox  
proxmox-backup-client backup user.pxar:/home/admin/ --repository backup  
HQ-SRV vim /etc/openssh/sshd_config  
CLI-HQ-R alterator 100.64.2.2:22 > 172.16.1.2:2222  
ssh user@172.16.1.2  
100.64.1.1 alterator внутренние сети 100.64.1.2 no ssh  


