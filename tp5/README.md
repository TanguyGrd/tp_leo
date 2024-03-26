$ /srv/idcard/idcard.sh
Machine name : tanguy
OS Rocky Linux and kernel version is 9.2 (Blue Onyx)
IP : ...
RAM :487Mi memory available on 759Mi total memory
Disk : 2.2G space left
Top 5 processes by RAM usage :
  - python3
  - NetworkManager
  - systemd
  - systemd
  - systemd-udevd
Listening ports :
  - 22 tcp : sshd
  - 68 udp : NetworkManager
  - ...
PATH directories :
  - /home/tanguy/.local/bin
  - /home/tanguy/bin
  - /usr/local/bin
  - /usr/bin
  - /usr/local/sbin
  - /usr/sbin


part 1 


#!/bin/bash
Tanguy
05/03/2024
name=$(youtube-dl --skip-download --get-title --no-warnings $1)
description=$(youtube-dl --skip-download --get-description --no-warnings $1)
video_folder="/srv/yt/${videoName}"

mkdir -p "${video_folder}"
echo $description > "${video_folder}/description"
youtube-dl -f mp4 -o "${video_folder}/%(title)s-%(id)s.%(ext)s" --no-warnings $1 >> /dev/null
echo "Video ${1} was downloaded."
echo "File path : ${video_folder}"
if [ ! -d "/var/log/yt" ]; then
    exit
fi

echo "[$(date +"%y/%m/%d %H:%M:%S")] Video ${1} was downloaded. File path : ${video_folder}" >> "/var/log/yt/download.log"
<<<<<<< HEAD

### 2.
#### 🌞 Vous fournirez dans le compte-rendu, en plus des fichiers :

```
$ systemctl status yt
○ yt.service - Service permettant de télécharger les vidéos youtubes listées dans le fichier toDownload
     Loaded: loaded (/etc/systemd/system/yt.service; disabled; preset: enabled)
     Active: inactive (dead)
TriggeredBy: ● yt.timer
```

```
$ sudo journalctl -xe -u yt -f 
Mar 04 17:03:01 systemd[1]: Started yt.service - Service permettant de télécharger les vidéos youtubes listées dans le fichier toDownload.
░░ Subject: A start job for unit yt.service has finished successfully
░░ Defined-By: systemd
░░ Support: https://www.debian.org/support
░░ 
░░ A start job for unit yt.service has finished successfully.
░░ 
░░ The job identifier is 6064.
Mar 04 17:03:15  yt-v2.sh[29848]: Video https://www.youtube.com/watch?v=RbkmGDaH0xc was downloaded.
Mar 04 17:03:15 yt-v2.sh[29848]: File path : /srv/yt/downloads/Je réponds aux questions !!
Mar 04 17:03:15 systemd[1]: yt.service: Deactivated successfully.
░░ Subject: Unit succeeded
░░ Defined-By: systemd
░░ Support: https://www.debian.org/support
░░ 
░░ The unit yt.service has successfully entered the 'dead' state.
```
=======
>>>>>>> e5892a015839ec80ab03f7a3ab3e9fa837610584
