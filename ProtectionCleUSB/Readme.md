# Suppression Write Protect On

### Prise des infos

		udevadm info /dev/sdb -a | head -n 100000
		lsmod | grep usb
		lsmod | grep usb
		sudo lsmod | grep usb_storage

		lsusb
		dmesg | grep -A 4 'idVendor=0951, idProduct=1642'
		sudo cat /sys/kernel/debug/usb/devices | grep -C 3 'Vendor=0951 ProdID=1642'
		cat /sys/bus/usb/devices/*/product
		cat /sys/bus/usb/devices/*/manufacturer

		lsusb
		### Bus 001 Device 003: ID 0951:1642 Kingston Technology DT101 G2
		udevadm info -a -p $(udevadm info -q path -n /dev/bus/usb/001/003)




### Supprimer le module usb_storage

		sudo modprobe -r $(lsmod | sed -n 's:,: :g ; s,^usb_storage[ 0-9]*,,p') usb_storage

### Modification
 
		lsusb
		sudo modprobe usb_storage quirks=0781:5583:w