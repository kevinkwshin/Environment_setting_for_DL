# Install Tensorflow on Ubuntu (16.04)

<p>
   <code>
      
      ubiquity -b
      #partition settings
      swap : primary, 8192 (recommanded)
      root : logical, rest (recommanded)
  </code>
</p>


<p>
  <code>
     
    # after installing, do not reboot. open terminal and run below codes
     
    sudo mount /dev/sdXY /mnt #sdXY --> ex)sda5

    sudo mount --bind /dev /mnt/dev &&
    sudo mount --bind /dev/pts /mnt/dev/pts &&
    sudo mount --bind /proc /mnt/proc &&
    sudo mount --bind /sys /mnt/sys

    sudo chroot /mnt

    grub-install /dev/sdX #sdX --> sda
    grub-install --recheck /dev/sdX #sdX -->sda
    update-grub
  </code>
</p>
