
netstat -na

Get-NetTCPConnection | ? {$_.State -eq "Listen"}

https://sysnetdevops.com/2017/04/24/exploring-the-powershell-alternative-to-netstat/