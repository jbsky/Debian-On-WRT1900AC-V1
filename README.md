# Debian Kernel for Linksys WRT1900AC V1

## How to make you own kernel?
=> arch debian i386 or amd64, open a term :<BR />
* `apt-get install git fakeroot build-essential ncurses-dev xz-utils libssl-dev bc liblz4-tool kernel-package u-boot-tools`<BR />
* `wget https://raw.githubusercontent.com/jbsky/Debian-On-WRT1900AC-V1/master/kernel-4.9.60/prekernel`<BR />
* `wget https://raw.githubusercontent.com/jbsky/Debian-On-WRT1900AC-V1/master/kernel-4.9.60/kernel`<BR />
* `wget https://raw.githubusercontent.com/jbsky/Debian-On-WRT1900AC-V1/master/menu`<BR />
* `chmod +x prekernel`<BR />
* `chmod +x kernel`<BR />
* `chmod +x menu`<BR />
* Edit scripts to adjust vars.<BR />
* `./prekernel`<BR />
* `cd linux`<BR />
* Need to go into menu?
* `../menu`<BR />
* Go compiling...<BR />
* `../kernel`<BR />
* After compiling, new firmware is Firmware-WRT1900AC-V1
* modules are in module/*


## How to make you own file system?
=> arch debian i386 or amd64, open a term :<BR />
* `apt-get install debootstrap  qemu-user-static arm-none-eabi*`<BR />
* `wget https://raw.githubusercontent.com/jbsky/Debian-On-WRT1900AC-V1/master/fs/dofs`<BR />
* `chmod +x dofs`<BR />
* Edit script to adjust vars.<BR />
* `./dofs`<BR />

## How to flash?
see https://github.com/Chadster766/McWRT/wiki/Flashing-Firmware-using-a-USB-to-TTL-Cable<BR />
=> update U-Boot Env<BR />
`marvell>>setenv pri_kern_size 0x2800000`<BR />
`marvell>>setenv alt_kern_size 0x2800000`<BR />
`marvell>>setenv flash_alt_image 'tftp ${default_load_addr} ${firmware_name}; nand erase ${alt_kern_addr} ${alt_kern_size};nand write ${default_load_addr} ${alt_kern_addr} ${filesize};'`<BR />
`marvell>>setenv flash_alt_image 'tftp ${default_load_addr} ${firmware_name}; nand erase ${alt_kern_addr} ${alt_kern_size};nand write ${default_load_addr} ${alt_kern_addr} ${filesize};'`<BR />
`marvell>>setenv flash_pri_image 'tftp ${default_load_addr} ${firmware_name}; nand erase ${pri_kern_addr} ${pri_kern_size};nand write ${default_load_addr} ${pri_kern_addr} ${filesize};'`<BR />
`marvell>>saveenv`<BR />

## fancontrol implementation.
Tmin=50<BR />
Tmax=80<BR />
Vmax=255<BR />
V=Vmax*(CurTemp-Tmin)/(Tmax-Tmin)<BR />
![image](https://github.com/jbsky/Debian-On-WRT1900AC-V1/blob/master/fancontrol.jpg)
<BR />

## Firewall
Script is inspired from debian.org's forum.

## /etc/sysctl.conf
* add vm.min_free_kbytes = 16384

## MWLWIFI
Always latest

* Care with an Intel 7260AC client<BR />
Roaming => min<BR />
Power   => max<BR />

## gpio_keys
* see /usr/local/src/gpio_keys.c

## WPS
* not working
