### grep -o

```awk
    awk 'match($0, /group[[:blank:]]*=[[:blank:]]*[[:alnum:]]*/) {print substr($0, RSTART, RLENGTH)}' /path/to/file
```