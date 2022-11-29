# Proxmox-Arm

###
Install proxmox ve on arm64. 

[中文文档请参考](https://foxi.buduanwang.vip/virtualization/pve/1902.html/)

### Getting started

See: https://pve.proxmox.com/wiki/Install_Proxmox_VE_on_Debian_11_Bullseye and add apt source

```
echo "deb https://foxi.buduanwang.vip/pan/foxi/Virtualization/proxmox/foxi/ bullseye main">/etc/apt/sources.list.d/foxi.list
curl -L  https://foxi.buduanwang.vip/pan/foxi/Virtualization/proxmox/foxi/gpg.key |apt-key add 
```

You need first change dhcp to static and install ifupdown or ifupdown2 avoid losing network connectivity during installation( we remove the ifupdown2 in pve-manager depends, but we still recommend install it first).

### Proxmox Backup Server
```
echo "deb https://foxi.buduanwang.vip/pan/foxi/Virtualization/proxmox/foxi/ pbsarm main">/etc/apt/sources.list.d/foxi-pbs.list
curl -L  https://foxi.buduanwang.vip/pan/foxi/Virtualization/proxmox/foxi/gpg.key |apt-key add 
apt update && DEBIAN_FRONTEND=noninteractiv apt --no-install-recommends install proxmox-backup-server 
```

### devel Registry

```
echo "deb https://foxi.buduanwang.vip/pan/foxi/Virtualization/proxmox/foxi/ pvearmdev main">/etc/apt/sources.list.d/foxi-devel.list
curl -L  https://foxi.buduanwang.vip/pan/foxi/Virtualization/proxmox/foxi/gpg.key |apt-key add 
```

## Tested platform (arm64):
- Rockpi
- Raspberry Pi
- Amlogic TV box
- Kunpeng
- FT
- Ampere 

## features

- ramfb support.
- add more pice on vm,so we can hotplug and use more nets disks.(not perfect)
- set gic-version=host.
- tpm

## version
###pve
- public version = 7.3-3
- testing version = 7.3-3
###pbs
- public version = 2.3.1-1
- testing version = 2.3.1-1

