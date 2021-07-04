# Hashcat

```zsh
# You should always crack passwords on your physical host

./hashcat --example-hashes | grep -B5 "krb5asrep" # Check if that hash is known by hashcat, and get MODE

./hashcat -m 18200 hashes/blackfield /opt/wordlist/rockyou.txt
```