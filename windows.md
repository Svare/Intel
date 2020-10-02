## Get Password Expiration Date

```powershell
Get-ADUser -Filter {Enabled -eq $True -and PasswordNeverExpires -eq $False} -Properties "DisplayName", "msDS-UserPasswordExpiryTimeComputed" | Select-Object -Property "DisplayName", @{Name="PasswordExpires";Expression={[datetime]::FromFileTime($_."msDS-UserPasswordExpiryTimeComputed")}} | Sort-Object -Property "PasswordExpires"
```

## Write to a File

```powershell
"VwByAGkAdABlAC0ASABvAHMAdAAgACcAUABvAEMAJwAKAA==" | Out-File -FilePath poc -Encoding ascii
$exploit = Get-Content poc
powershell.exe -enc $exploit
```

```
```