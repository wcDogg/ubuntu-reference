# Ubuntu: System Info


```bash
# OS, version
cat /etc/os-release   
lsb_release -a

# OS, version, release, kernel, hostname, virtualization platform
hostnamectl

free -g     # Memory info
df -h       # Disk fee - available space on mounted drives
uname -a    # Kernel info - hostname, release, version, architecture

lspci       # List PCI devices
lsusb       # List USB devices
lspcmcia    # List PCMCIA cards
```