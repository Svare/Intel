```zsh
root@owncloud:~# certbot --apache
Saving debug log to /var/log/letsencrypt/letsencrypt.log
Plugins selected: Authenticator apache, Installer apache

Which names would you like to activate HTTPS for?
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
1: owncloud.seguridad.unam.mx
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Select the appropriate numbers separated by commas and/or spaces, or leave input
blank to select all options shown (Enter 'c' to cancel): 
Cert is due for renewal, auto-renewing...
Renewing an existing certificate for owncloud.seguridad.unam.mx
Performing the following challenges:
http-01 challenge for owncloud.seguridad.unam.mx
Waiting for verification...
Cleaning up challenges
Deploying Certificate to VirtualHost /etc/apache2/sites-enabled/owncloud.conf
Failed redirect for owncloud.seguridad.unam.mx
Unable to set enhancement redirect for owncloud.seguridad.unam.mx
Unable to find corresponding HTTP vhost; Unable to create one as intended addresses conflict; Current configuration does not support automated redirection

IMPORTANT NOTES:
 - We were unable to set up enhancement redirect for your server,
   however, we successfully installed your certificate.
 - Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/owncloud.seguridad.unam.mx/fullchain.pem
   Your key file has been saved at:
   /etc/letsencrypt/live/owncloud.seguridad.unam.mx/privkey.pem
   Your certificate will expire on 2021-06-11. To obtain a new or
   tweaked version of this certificate in the future, simply run
   certbot again with the "certonly" option. To non-interactively
   renew *all* of your certificates, run "certbot renew"
```
```
root@owncloud:~# cat renew_owncloudcert.sh
#!/bin/bash

echo ; date ; echo

/sbin/iptables -A INPUT -p tcp --dport 80 -j ACCEPT
/sbin/iptables -A INPUT -p tcp --dport 443 -j ACCEPT

/usr/sbin/a2ensite default-ssl.conf ; echo
/usr/sbin/a2ensite 000-default.conf ; echo
/etc/init.d/apache2 reload ; echo

echo -e "########## certbot ######################################################\n"

/usr/bin/certbot renew ; echo

echo -e "########## fin certbot ##################################################\n"

/usr/sbin/a2dissite default-ssl.conf ; echo
/usr/sbin/a2dissite 000-default.conf ; echo
/etc/init.d/apache2 restart ; echo

/root/iptables.sh
root@owncloud:~# crontab -l | tail -1
1 0 * * 6 /root/renew_owncloudcert.sh | mail -s "Owncloud Renew CRT" operacion@cert.unam.mx
```
```
https://certbot.eff.org/lets-encrypt/ubuntuxenial-apache
https://certbot.eff.org/docs/uninstall.html
```