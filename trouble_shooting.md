# 우분투 설치시1
/target/에 'grub-efi-amd64-signed' 패키지를 설치하는 데 실패했습니다. GRUB 부트로더 없이는 시스템이 부팅하지 않습니다.
https://askubuntu.com/questions/260297/why-12-04-fails-to-install-grub-efi-to-target/774537#774537

<pre><code>ubiquity -b
	
sudo mount /dev/sdXY /mnt

sudo mount --bind /dev /mnt/dev &&
sudo mount --bind /dev/pts /mnt/dev/pts &&
sudo mount --bind /proc /mnt/proc &&
sudo mount --bind /sys /mnt/sys

sudo chroot /mnt

grub-install /dev/sdX

grub-install --recheck /dev/sdX

update-grub
</pre></code>

# 우분투 설치시2
E: Could not get lock /var/lib/dpkg/lock - open (11: Resource temporarily unavailable)
E: Unable to lock the administration directory (/var/lib/dpkg/), is another process using it?

https://www.hahwul.com/2016/08/debian-apt-get-could-not-get-lock.html

https://itsfoss.com/fix-ubuntu-install-error/
<code><pre>
sudo rm /var/lib/apt/lists/lock
sudo rm /var/cache/apt/archives/lock
sudo rm /var/lib/dpkg/lock
dpkg --configure -a
</pre></code>

# 우분투 터미널 원격접속 설정
<code><pre>unbuntu remote using putty
sudo su
apt-get install ssh
nano /etc/ssh/sshd_config
Port 1984
service ssh restart
</pre></code>
from 
https://www.youtube.com/watch?v=cXygRsXOFtc


mount: wrong fs type, bad option, bad superblock on 192.168.1.5:/home/shared, missing codepage or helper program, or other error (for several filesystems (e.g. nfs, cifs) you might need a /sbin/mount.<type> helper program)  
In some cases useful info is found in syslog - try dmesg | tail or so.
The error message mentions:

(for several filesystems (e.g. nfs, cifs) you might need a /sbin/mount. helper program)

This is relevant given that you are trying to mount NFS. The /sbin/mount.nfs helper program is provided by nfs-common. You can install it with:

sudo apt install nfs-common
On the other hand, if you are trying to mount CIFS, the helper program is provided by cifs-utils. You can install it with:

sudo apt install cifs-utils
