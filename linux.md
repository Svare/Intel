sudo update-alternatives --config editor

jeipi ALL=(ALL:ALL) NOPASSWD:ALL

## Force DHCP Client (dhclient) to Renew IP Address

```zsh
sudo dhclient -v -r eth0
sudo dhclient -v eth0

sudo systemctl restart network.service
sudo systemctl status network.service

nmcli conn
nmcli conn down id "ID"
nmcli conn up id "ID"
```

## Get Bytes of a String with \x Prepended

```zsh
echo -n 'PoC' | xxd -p | sed -r 's/(..)/\\x\1/g'

# https://stackoverflow.com/questions/7568112/split-large-string-into-substrings
```

## tar

```zsh
#Compress
tar -czvf /path/filename.tar.gz /path/to/dir1 dir2 file1 file2
#Uncompress
tar -xzvf filename.tar.gz -C /path/

# https://www.cyberciti.biz/faq/how-to-create-tar-gz-file-in-linux-using-command-line/
```

## cut

```zsh
# Get first 100 chars from a file

cut -c 1-100 input      # Each Line
cut -c -100 input       # Each Line
cut -c -100 -z input    # Use NULL as Delimeter
```

## ip

```

Remove IP from Network Adapter

ip addr del 10.22.30.44/16 dev eth0

Remove all IPs from Network Adapter

ip addr flush dev eth0

```