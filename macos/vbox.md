VirtualBox
==========

Создание Raw-диска
------------------

 * загрузиться в gparted и создать желаемый mbr-диск c ext4-разделом;
 * `$ sudo dd if=/dev/disk1 of=~/VirtualBoxVMs/disk1.mbr bs=512 count=1`
 * `$ sudo chown root:admin /dev/disk1 /dev/disk1s1 && sudo chmod 660 /dev/disk1 /dev/disk1s1`
 * `$ VBoxManage internalcommands createrawvmdk -filename ~/VirtualBoxVMs/disk1s1.vmdk -rawdisk /dev/disk1 -partitions 1 -mbr ~/VirtualBoxVMs/disk1.mbr`
 * в настройкам ВМ обязательно отметить "Use Host I/O Cache" в настройках диска
