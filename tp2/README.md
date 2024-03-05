# tp_leo

1. Find me

🌞 Trouver le chemin vers le répertoire personnel de votre utilisateur
/home/tanguy

🌞 Trouver le chemin du fichier de logs SSH
var/log

🌞 Trouver le chemin du fichier de configuration du serveur SSH
cat /etc/ssh/ssh_config

II. Users
🌞 Créer un nouvel utilisateur
sudo useradd -d /home/papier_alu -p chocolat marmotte

🌞 Prouver que cet utilisateur a été créé
[tanguy@localhost /]$ cat /etc/passwd | grep marmotte marmotte:x:1001:1001::/home/papier_alu:/bin/bash

🌞 Déterminer le hash du password de l'utilisateur marmotte
marmotte:$6$uk7hVOEkHZ72qxbs$NbbUxPdY3w7mbilwIhQeCq7QMJ1PUmWeIUtqit3rRcEU8yYKquTDYKSE9QIuzE12hJNN8peCMgrHXDh8NL95d.:19744:0:99999:7:::

Hint sur la ligne de commande
Connexion sur le nouvel utilisateur
🌞 Tapez une commande pour vous déconnecter : fermer votre session utilisateur
[tanguy@localhost /]$ exit logout Connection to 192.168.245.3 closed.

Partie 2 : Programmes et paquets
1. Run then kill
🌞 Lancer un processus sleep
sleep 1000

et j'ai utiliser la commande ps -ef | grep sleep

🌞 Terminez le processus sleep depuis le deuxième terminal
kill PID (1525)

🌞 Lancer un nouveau processus sleep, mais en tâche de fond
sleep 1000 &

🌞 Visualisez la commande en tâche de fond
[tanguy@localhost ~]$ jobs [1]+ Running sleep 1000 & [tanguy@localhost ~]$

3. Find paths
🌞 Trouver le chemin où est stocké le programme sleep
[tanguy@localhost ~]$ which sleep /usr/bin/sleep

🌞 Tant qu'on est à chercher des chemins : trouver les chemins vers tous les fichiers qui s'appellent .bashrc
[tanguy@localhost home]$ sudo find / -name .bashrc /etc/skel/.bashrc /root/.bashrc /home/tanguy/.bashrc /home/papier_alu/.bashrc

4. La variable PATH
🌞 Vérifier que les commandes sleep, ssh, et ping sont bien des programmes stockés dans l'un des dossiers listés dans votre PATH
[tanguy@localhost home]$ sudo find / -name sleep /usr/bin/sleep [tanguy@localhost home]$ sudo find / -name ssh /etc/ssh /var/lib/selinux/targeted/active/modules/100/ssh /usr/bin/ssh [tanguy@localhost home]$ sudo find / -name ping /usr/bin/ping /usr/sbin/ping [tanguy@localhost home]$

II. Paquets
