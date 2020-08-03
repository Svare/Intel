
## Creating a Self Signed Certificate for Code Signing

New-SelfSignedCertificate -Subject "CN=Jeipi Code Signing" -Type CodeSigningCert -KeySpec "Signature" -KeyUsage "DigitalSignature" -FriendlyName "Jeipi Code Signing" -NotAfter (Get-Date).AddYears(1) -CertStoreLocation Cert:\CurrentUser\TrustedPublisher\

New-SelfSignedCertificate -DnsName email@yourdomain.com -Type CodeSigning -CertStoreLocation cert:\CurrentUser\My

### Ref

    https://stackoverflow.com/questions/31772109/makecert-missing-from-windows-10-and-visual-studio-2015-install

## Signing a Script

Set-AuthenticodeSignature -FilePath C:\Users\Jeipi\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1 -Certificate (Get-ChildItem Cert:\CurrentUser\TrustedPublisher\ | Where-Object { $_.Subject -eq "CN=Jeipi Code Signing" })

El certificado debe de estar en:

    Cert:\CurrentUser\Root\
    Cert:\CurrentUser\TrustedPublisher\

## Remove Certificate

Get-ChildItem Cert:\CurrentUser\My | Where-Object { $_.Subject -eq "CN=Jeipi Code Signing" } | Remove-Item

### Ref

    http://blog.dbsnet.fr/remove-certificates-using-powershell