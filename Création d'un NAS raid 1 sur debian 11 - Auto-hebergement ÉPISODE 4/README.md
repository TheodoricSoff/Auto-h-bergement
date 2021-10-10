su root

lsblk

fdisk /dev/"disk"

Appuyer sur "p"

Appuyer sur "d"

Validé avec "w"

lsblk

La méme chose pour les autres disques.

sudo apt update

sudo apt upgrade

sudo apt install mdadm samba samba-common cifs-utils

lsblk

CREATION DU RAID :

mdadm --create /dev/md0 --level=1 --raid-devices=2 /dev/"disk1" /dev/"disk2"

cat /proc/mdstat

lsblk

mkfs.ext4 -F /dev/md0

Montage des disques

mkdir /raid

mount /dev/md0 /raid

cd /raid

df -h | grep /raid

mkdir /data

mount /dev/"disk" /data

df -h | grep /data

sudo mdadm --detail --scan | sudo tee -a /etc/mdadm/mdadm.conf

sudo update-initramfs -u

echo '/dev/"disk" /data ext4 defaults,nofail,discard 0 0' | sudo tee -a /etc/fstab

echo '/dev/"diskraid" /raid ext4 defaults,nofail,discard 0 0' | sudo tee -a /etc/fstab

addgroup raid

addgroup data

adduser "user" data
adduser "user" raid

sudo chown root:raid /raid 
sudo chown root:data /data

sudo chmod 775 /data
sudo chmod 775 /raid

mkdir /raid/data
mkdir /data/data

chmod 775 /raid/data
chmod 775 /data/data

chown root:raid /raid /raid/data
chown root:data /data /data/data

ls -l /data
ls -l /raid

Configuration de samba : 

sudo cp /etc/samba/smb.conf /etc/samba/smb.conf.save

nano /etc/samba/smb.conf

Ajouter a la fin le contenue du fichier "smb.conf"

systemctl reload smbd.service

useradd "user"

adduser "user" raid
adduser "user" data

smbpasswd -a "user"

mdadm -D /dev/md0

cat /proc/mdstat