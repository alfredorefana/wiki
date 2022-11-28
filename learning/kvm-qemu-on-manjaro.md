# How to Install KVM/QEMU on Manjaro/Archlinux


## Definitions

### KVM

KVM is an acronym of Kernel-based Virtual Machine, it is a technology solution for virtualization based on the Linux kernel module.
The KVM technology will turn the Linux machine into hypervisor virtualization, which is called the host machine. On the host machine, you will be able to create multiple isolated systems called virtual machines (VM). 


### QEMU

QEMU or Quick Emulator is an open-source system emulator and virtualizer for hardware virtualization. Generally, it is used as a virtualizer with the KVM kernel module to run virtual machines. 


## Checking System Architecture & CPU Virtualization Support

1. Execute the following command to check the system architecture of your system.

```
uname -a
```

2. Your output will look like this, and pay attention to the "x86_64" or "64-bit" architecture

```
Linux MiPro-Manjaro 5.15.78-1-MANJARO #1 SMP PREEMPT Thu Nov 10 20:50:09 UTC 2022 x86_64 GNU/Linux
```

3. Check the hardware virtualization support by running the following command.

```
sudo lscpu | grep Virtualization
```

4. Search for Kernel Module

```
zgrep CONFIG_KVM /proc/config.gz
```
Example output:
```
CONFIG_KVM_GUEST=y
CONFIG_KVM_MMIO=y
CONFIG_KVM_ASYNC_PF=y
CONFIG_KVM_VFIO=y
CONFIG_KVM_GENERIC_DIRTYLOG_READ_PROTECT=y
CONFIG_KVM_COMPAT=y
CONFIG_KVM_XFER_TO_GUEST_WORK=y
CONFIG_KVM=m
CONFIG_KVM_INTEL=m
CONFIG_KVM_AMD=m
CONFIG_KVM_AMD_SEV=y
CONFIG_KVM_XEN=y
CONFIG_KVM_MMU_AUDIT=y
```
If you are using an AMD processor, you should see CONFIG_KVM_AMD (or CONFIG_KVM_INTEL if you are using intel) followed by =y or =m, then you are good to go.

5. You can also check how much memory and free disk space you have

```
free -h
df -h
```


## Installation

1. Check and update your system

```
sudo pacman -Syy
```

2. Installing Arch linux keyring

```
sudo pacman -S archlinux-keyring
```

3. QEMU and dependencies Installation

```
sudo pacman -S qemu-desktop qemu-arch-extra ovmf bridge-utils dnsmasq vde2 openbsd-netcat ebtables iptables libvirt
```

Below are essential packages you must know:

- qemu: An open-source machine emulator and virtualizer.
- ovmf: helps to do the UEFI Bios and Secure Boot setups.
- bridge-utils: Utilities for configuring Linux network bridge needed for VMs.
- vde2: for QEMU distributed ethernet emulation
- dnsmasq: Lightweight DNS forwarder and DHCP server.
- virt-manager: A GUI application for managing virtual machines.
- openbsd-netcat network testing tool (Optional)
- ebtables and iptables to create packet routing and firewalls
- libvirt: An API for controlling virtualization engines such as KVM, QEMU, etc.



4. Install Virt-Manager and libvirtd Service

```
sudo pacman -S virt-manager virt-viewer
```

- Virt-manager is a UI that helps to create and organize the VM’s. 
- And virt-viewer is used to open remote window into the VM instance.


5. Install libguestfs

```
sudo pacman -S libguestfs
```

libguestfs is a set of tools used to access and modify virtual machine (VM) disk images. You can use this for:
- viewing and editing files inside guests
- scripting changes to VMs
- monitoring disk used/free statistics
- creating guests
- P2V
- V2V
- performing backup e.t.c


6. Enable and Start for at boot KVM libvirt service

```
sudo systemctl enable libvirtd.service
sudo systemctl start libvirtd.service
```

7. Add user to libvirt group to use the system-level virtual machines (qemu:///system)

```
sudo usermod -a -G libvirt $USER
```


## Configure the KVM

Open the ```/etc/libvirt/libvirtd.conf``` for editing

```
sudo nano -cl /etc/libvirt/libvirtd.conf
```

Here are the Lines to Edit:

1. Uncomment the line 85 or so:
```
unix_sock_group = "libvirt"
```

2. Uncomment the line 108 or so:
```
unix_sock_rw_perms = "0770" 
```

Make sure to save the file before you exit.


## Creating an New Network Bridge for VM

A new network bridge is needed allow a separate IP subnet for Guest OS’s in VM.



## Testing