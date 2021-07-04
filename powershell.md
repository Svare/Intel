
## Wipe File Contents

```powershell
    $null | Out-File ./file.txt
```

## DEC,HEX,OCT -> ASCII

```powershell
[char][byte]0x40
[char][byte]64
[Convert]::ToString(15, 2)
1111
[Convert]::ToInt32(1111, 2)
15
```

https://www.pipehow.tech/convert-numeralsystems/

https://docs.microsoft.com/en-us/powershell/scripting/samples/using-format-commands-to-change-output-view?view=powershell-7

## Hyper-V

```powershell
    # Get the name of all VMs in Hyper-V
        Get-VM
    # Copy file to a VM in Hyper-V (It is mandatory to enable Guest services)
        Copy-VMFile "Windows 10 Pro x64 OpenShift" -SourcePath .\crc-windows-amd64.zip -DestinationPath "C:\Users\Prueba\Desktop" -CreateFullPath -FileSource Host
```