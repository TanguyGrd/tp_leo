## 🌞 S'assurer que le service sshd est démarré

`systemctl status sshd`

## 🌞 Analyser les processus liés au service SSH

`ps -ef et ps -ef | grep sshd`

## 🌞 Déterminer le port sur lequel écoute le service SSH

`[tanguy@node1 ~]$ sudo ss -anpt
State   Recv-Q  Send-Q   Local Address:Port   Peer Address:Port  Process
LISTEN  0       128            0.0.0.0:22          0.0.0.0:*      users:(("sshd",pid=682,fd=3))
ESTAB   0       0            10.2.1.11:22         10.2.1.1:54372  users:(("sshd",pid=1340,fd=4),("sshd",pid=1336,fd=4))
LISTEN  0       128               [::]:22             [::]:*      users:(("sshd",pid=682,fd=4))`

## 🌞 Consulter les logs du service SSH
`[tanguy@node1 ~]$ journalctl -xe -u sshd`
`[tanguy@node1 log]$ sudo tail -n 10 /var/log/secure`

# 2. Modification du service

## 🌞 Identifier le fichier de configuration du serveur SSH

`le fichier de config du serveur ssh c'est sshd_config`

## 🌞 Modifier le fichier de conf

`[tanguy@node1 ssh]$ sudo cat sshd_config | grep 1025`

`[tanguy@node1 ssh]$ sudo firewall-cmd --remove-service=ssh --permanent
success`

## 🌞 Redémarrer le service
`sudo systemctl restart sshd`
