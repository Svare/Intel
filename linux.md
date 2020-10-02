sudo update-alternatives --config editor

jeipi ALL=(ALL:ALL) NOPASSWD:ALL

## Get Bytes of a String with \x Prepended

```zsh
echo -n 'PoC' | xxd -p | sed -r 's/(..)/\\x\1/g'

# https://stackoverflow.com/questions/7568112/split-large-string-into-substrings
```

## cut

```zsh
# Get first 100 chars from a file

cut -c 1-100 input      # Each Line
cut -c -100 input       # Each Line
cut -c -100 -z input    # Use NULL as Delimeter
```