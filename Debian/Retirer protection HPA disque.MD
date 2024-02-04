# Installation du paquet disktype Non obligatoire

sudo apt install disktype

# Infos disque

df -TH
lsblk -S
sudo hdparm -I /dev/sda
sudo hdparm -N /dev/sda
sudo disktype /dev/sda

# Check ro ou rw

sudo hdparm -r /dev/sda

# Activer Read Only

sudo hdparm -r1 /dev/sda

# Désactiver Read Only (rw)

sudo hdparm -r0 /dev/sda