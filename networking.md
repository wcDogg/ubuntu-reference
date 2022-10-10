# Ubuntu: Networking


```bash
ip addr
ifconfig


# Internal IPv4 gateway
ip -4 route show default | awk '{print $3}' 
# Internal IPv6 gateway
ip -6 route show default | awk '{print $3}' 
```