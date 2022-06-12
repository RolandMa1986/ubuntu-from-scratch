qemu-system-x86_64 -drive format=raw,system.img 


sudo losetup /dev/loop7 system.img

sudo kpartx -a /dev/loop7

sudo mount /dev/mapper/loop7p1 loop7p1
sudo mount /dev/mapper/loop7p2 loop7p2


VBoxManage convertfromraw --format VDI  system.img system.vdi


qemu-img convert -f raw -O qcow2 image.img image.qcow2