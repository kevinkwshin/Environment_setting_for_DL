# Install Tensorflow on Ubuntu (16.04)

<code>
ubiquity -b

sudo mount /dev/sdXY /mnt

sudo mount --bind /dev /mnt/dev &&
sudo mount --bind /dev/pts /mnt/dev/pts &&
sudo mount --bind /proc /mnt/proc &&
sudo mount --bind /sys /mnt/sys

sudo chroot /mnt

grub-install /dev/sdX

grub-install --recheck /dev/sdX

update-grub
</code>
