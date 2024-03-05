## Partie 1 : Partitionnement du serveur de stockage


### 🌞 Partitionner le disque à l'aide de LVM

`sudo pvcreate /dev/sdb /dev/sdc
 sudo vgcreate storage /dev/sdb
 sudo lvcreate -l 100%FREE data -n last_data`


 ### 🌞 Formater la partition

 ` sudo mkfs -t ext4 /dev/storage/last_data`

 ### 🌞 Monter la partition

`[tanguy@localhost ~]$ sudo mount /dev/storage/last_data
mount: /dev/storage/last_data: can't find in /etc/fstab.`

`[tanguy@localhost ~]$ df -h | grep last_data
/dev/mapper/storage-last_data  8.7G   24K  8.2G   1% /storage`

` sudo mount -av`

reboot 
