## Redirect with tftp
```
show running-config | redirect tftp://10.0.1.192/running-config.bkp
```
## Copy with tftp
```
copy running-config tftp://10.0.1.192/running_config.bkp
```
## Redirect with scp
```
show crypto session detail | redirect scp://root@10.0.1.192//tmp/connected.intel
```

