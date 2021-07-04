# Test RCE

```zsh
# Attacker
    tcpdump -i tun0 icmp
# Target
    ping -c 1 10.10.10.10
```