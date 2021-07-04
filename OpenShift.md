```powershell
PS C:\Users\Jeipi> crc stop

    INFO Stopping the OpenShift cluster, this may take a few minutes...
    Stopped the OpenShift cluster                                                                                                                             PS C:\Users\Jeipi> crc delete                                                                                                                             Do you want to delete the OpenShift cluster? [y/N]: y                                                                                                     Deleted the OpenShift cluster

PS C:\Users\Jeipi> crc cleanup

    INFO Uninstalling tray if installed
    INFO Uninstalling daemon if installed
    INFO Removing the crc VM if exists
    INFO Removing dns server from interface
    INFO Will run as admin: Remove dns entry for default switch
    INFO Removing pull secret from the keyring
    INFO Removing older logs
    INFO Removing CRC Machine Instance directory
    Cleanup finished
```
```
Borrar la carpeta $HOME/.crc
Borrar el Virtual Switch crc
Reconfigurar las entradas en C:\Windows\System32\drivers\etc\hosts
    # OpenShift
    192.168.8.48	api.crc.testing
    192.168.8.48	foo.apps-crc.testing
    192.168.8.48	oauth-openshift.apps-crc.testing
    192.168.8.48	console-openshift-console.apps-crc.testing
    192.168.8.48	nodejs-ex-git-myproject.apps-crc.testing
```
```zsh
    crc setup --log-level debug
```
```
PS C:\Users\Jeipi> crc setup --log-level debug
DEBU CodeReady Containers version: 1.22.0+6faff76f
DEBU OpenShift version: 4.6.15 (embedded in executable)
DEBU Running 'crc setup'
INFO Checking if podman remote executable is cached
DEBU Currently podman remote is not supported
INFO Checking if admin-helper executable is cached
DEBU Running 'C:\Users\Jeipi\.crc\bin\admin-helper-windows.exe --version'
DEBU Found admin-helper-windows.exe version 0.0.2
DEBU admin-helper executable already cached
INFO Checking if CRC bundle is extracted in '$HOME/.crc'
INFO Checking if C:\Users\Jeipi\.crc\cache\crc_hyperv_4.6.15.crcbundle exists
DEBU Copying 'C:\Users\Jeipi\.crc\cache\crc_hyperv_4.6.15\oc.exe' to 'C:\Users\Jeipi\.crc\bin\oc\oc.exe'
DEBU C:\Users\Jeipi\.crc\cache\crc_hyperv_4.6.15.crcbundle exists
INFO Checking minimum RAM requirements
DEBU Total memory of system is 34195279872 bytes
INFO Checking if running as normal user
INFO Checking Windows 10 release
INFO Checking Windows edition
DEBU Running on Windows ProfessionalEducation edition
INFO Checking if Hyper-V is installed and operational
INFO Checking if user is a member of the Hyper-V Administrators group
INFO Checking if Hyper-V service is enabled
INFO Checking if the Hyper-V virtual switch exist
INFO Found Virtual Switch to use: crc
Setup is complete, you can now run 'crc start' to start the OpenShift cluster
```
```zsh
crc start -p pull-secret.txt --log-level debug
```
```
PS C:\Users\Jeipi> crc start -p .\Documents\deleteme\pull-secret.txt --log-level debug
DEBU CodeReady Containers version: 1.22.0+6faff76f
DEBU OpenShift version: 4.6.15 (embedded in executable)
DEBU Running 'crc start'
DEBU Total memory of system is 34195279872 bytes
DEBU Copying 'C:\Users\Jeipi\.crc\cache\crc_hyperv_4.6.15\oc.exe' to 'C:\Users\Jeipi\.crc\bin\oc\oc.exe'
WARN A new version (1.23.1) has been published on https://cloud.redhat.com/openshift/install/crc/installer-provisioned
INFO Checking if podman remote executable is cached                                                                     DEBU Currently podman remote is not supported                                                                           INFO Checking if admin-helper executable is cached                                                                      DEBU Running 'C:\Users\Jeipi\.crc\bin\admin-helper-windows.exe --version'                                               DEBU Found admin-helper-windows.exe version 0.0.2                                                                       DEBU admin-helper executable already cached
INFO Checking minimum RAM requirements
DEBU Total memory of system is 34195279872 bytes
INFO Checking if running as normal user
INFO Checking Windows 10 release
INFO Checking Windows edition
DEBU Running on Windows ProfessionalEducation edition
INFO Checking if Hyper-V is installed and operational
INFO Checking if user is a member of the Hyper-V Administrators group
INFO Checking if Hyper-V service is enabled
INFO Checking if the Hyper-V virtual switch exist
INFO Found Virtual Switch to use: crc
DEBU Checking file: C:\Users\Jeipi\.crc\machines\crc\.crc-exist
DEBU Copying 'C:\Users\Jeipi\.crc\cache\crc_hyperv_4.6.15\oc.exe' to 'C:\Users\Jeipi\.crc\bin\oc\oc.exe'
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                       Off
DEBU [stderr =====>] :
INFO Starting CodeReady Containers VM for OpenShift 4.6.15...
DEBU Updating CRC VM configuration
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Start-VM crc
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU Waiting for host to start...
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
              ====>] : 192.168.8.48
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
              ====>] : 192.168.8.48
DEBU [stderr =====>] :
DEBU Waiting until ssh is available
DEBU retry loop: attempt 0
DEBU About to run SSH command:
exit 0
DEBU Using ssh private keys: [C:\Users\Jeipi\.crc\cache\crc_hyperv_4.6.15\id_ecdsa_crc C:\Users\Jeipi\.crc\machines\crc\id_ecdsa]
DEBU SSH command results: err: <nil>, output:
INFO CodeReady Containers VM is running
DEBU About to run SSH command:
cat /home/core/.ssh/authorized_keys
DEBU SSH command results: err: <nil>, output: ecdsa-sha2-nistp521 AAAAE2VjZHNhLXNoYTItbmlzdHA1MjEAAAAIbmlzdHA1MjEAAACFBACMuE90nHtL9uhvqlqi6EWxpEqRZTTHdyem2+IWU7cNGAwEnK5jgUv1oRid3Zt6eOo+HeuvA8H5Z/P7kfPu3haENQCKrOmERQkD+qDOzA/K/53YzEMS0J29FRAEiLfUUA0XbCW8Jggxp4SUN4lF36u9WMGXv5gW+jndnTDg9Izs8Xju/g==

DEBU About to run SSH command:
sudo xfs_growfs / >/dev/null
DEBU SSH command results: err: <nil>, output:
INFO Starting network time synchronization in CodeReady Containers VM
DEBU About to run SSH command:
sudo timedatectl set-ntp on
DEBU SSH command results: err: <nil>, output:
DEBU Creating /var/srv/dnsmasq.conf with permissions 0644 in the CRC VM
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU About to run SSH command:
sudo podman rm -f dnsmasq
DEBU SSH command results: err: <nil>, output: f81dc40ca965de4096fbaf8c3ca2d7130bf3ffeb192f9f00005542207fbc88e4
DEBU About to run SSH command:
sudo rm -f /var/lib/cni/networks/podman/10.88.0.8
DEBU SSH command results: err: <nil>, output:
DEBU About to run SSH command:
sudo podman run  --ip 10.88.0.8 --name dnsmasq -v /var/srv/dnsmasq.conf:/etc/dnsmasq.conf -p 53:53/udp --privileged -d quay.io/crcont/dnsmasq:latest
DEBU SSH command results: err: <nil>, output: 2d7ee940483bbf1efc4fda02502d37a875d9086a238021c9cdb798faaee48dba
INFO Will run as admin: add dns server address to interface vEthernet (crc)
DEBU About to run SSH command:
cat /etc/resolv.conf
DEBU SSH command results: err: <nil>, output: # Generated by NetworkManager
search lan
nameserver 192.168.8.1
nameserver 2001::1
DEBU Creating /etc/resolv.conf with permissions 0644 in the CRC VM
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU retry loop: attempt 0
DEBU About to run SSH command:
host -R 3 foo.apps-crc.testing
DEBU SSH command results: err: <nil>, output: foo.apps-crc.testing has address 192.168.8.48
INFO Check internal and public DNS query ...
DEBU About to run SSH command:
host -R 3 quay.io
DEBU SSH command results: err: <nil>, output: quay.io has address 34.197.63.98
quay.io has address 3.213.173.170
quay.io has address 18.210.212.75
quay.io has address 50.16.140.223
quay.io has address 52.72.182.67
quay.io has address 34.224.196.237
quay.io has address 18.211.164.173
quay.io has address 34.224.196.162
quay.io mail is handled by 30 aspmx2.googlemail.com.
quay.io mail is handled by 30 aspmx3.googlemail.com.
quay.io mail is handled by 10 aspmx.l.google.com.
quay.io mail is handled by 20 alt1.aspmx.l.google.com.
quay.io mail is handled by 20 alt2.aspmx.l.google.com.
INFO Check DNS query from host ...
DEBU api.crc.testing resolved to [192.168.8.48]
DEBU foo.apps-crc.testing resolved to [192.168.8.48]
DEBU About to run SSH command:
test -e /var/lib/kubelet/config.json
DEBU SSH command results: err: Process exited with status 1, output:
INFO Adding user's pull secret to instance disk...
DEBU Using secret from configuration
DEBU Creating /var/lib/kubelet/config.json with permissions 0600 in the CRC VM
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
INFO Verifying validity of the kubelet certificates ...
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
INFO Starting OpenShift kubelet service
DEBU About to run SSH command:
sudo systemctl daemon-reload
DEBU SSH command results: err: <nil>, output:
DEBU About to run SSH command:
sudo systemctl start kubelet
DEBU SSH command results: err: <nil>, output:
INFO Kubelet client certificate has expired, renewing it... [will take up to 8 minutes]
DEBU retry loop: attempt 0
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 1
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 2
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 3
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 4
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 5
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 6
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 7
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 8
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 9
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 10
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 11
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 12
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 13
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: Process exited with status 1, output:
DEBU error: Temporary error: ssh command error:
command : oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 5s
DEBU retry loop: attempt 14
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: NAME        AGE   SIGNERNAME                                    REQUESTOR                                                                   CONDITION
csr-8flp2   36d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-q8zdg   37d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-t4km6   37d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
csr-xnpv9   36d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
DEBU error: Temporary error: No Pending CSR with signerName kubernetes.io/kube-apiserver-client-kubelet - sleeping 5s
DEBU retry loop: attempt 15
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: NAME        AGE   SIGNERNAME                                    REQUESTOR                                                                   CONDITION
csr-8flp2   36d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-q8zdg   37d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-t4km6   37d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
csr-xnpv9   36d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
DEBU error: Temporary error: No Pending CSR with signerName kubernetes.io/kube-apiserver-client-kubelet - sleeping 5s
DEBU retry loop: attempt 16
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: NAME        AGE   SIGNERNAME                                    REQUESTOR                                                                   CONDITION
csr-8flp2   36d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-q8zdg   37d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-t4km6   37d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
csr-xnpv9   36d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
DEBU error: Temporary error: No Pending CSR with signerName kubernetes.io/kube-apiserver-client-kubelet - sleeping 5s
DEBU retry loop: attempt 17
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: NAME        AGE   SIGNERNAME                                    REQUESTOR                                                                   CONDITION
csr-8flp2   36d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-q8zdg   37d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-t4km6   37d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
csr-xnpv9   36d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
DEBU error: Temporary error: No Pending CSR with signerName kubernetes.io/kube-apiserver-client-kubelet - sleeping 5s
DEBU retry loop: attempt 18
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: NAME        AGE   SIGNERNAME                                    REQUESTOR                                                                   CONDITION
csr-8flp2   36d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-q8zdg   37d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-t4km6   37d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
csr-xnpv9   36d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
DEBU error: Temporary error: No Pending CSR with signerName kubernetes.io/kube-apiserver-client-kubelet - sleeping 5s
DEBU retry loop: attempt 19
DEBU About to run SSH command:
oc get csr --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: NAME        AGE   SIGNERNAME                                    REQUESTOR                                                                   CONDITION
csr-2tfkz   1s    kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Pending
csr-8flp2   36d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-q8zdg   37d   kubernetes.io/kube-apiserver-client-kubelet   system:serviceaccount:openshift-machine-config-operator:node-bootstrapper   Approved,Issued
csr-t4km6   37d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
csr-xnpv9   36d   kubernetes.io/kubelet-serving                 system:node:crc-ctj2r-master-0
                    Approved,Issued
DEBU Approving pending CSRs
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU Approving csr csr-2tfkz (signerName: kubernetes.io/kube-apiserver-client-kubelet)
DEBU About to run SSH command:
oc adm certificate approve csr-2tfkz --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: certificatesigningrequest.certificates.k8s.io/csr-2tfkz approved
DEBU retry loop: attempt 0
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 1
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 2
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 3
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 4
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 5
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 6
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 7
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 8
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 9
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 10
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 11
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 12
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 13
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 14
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 15
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 16
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 17
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 18
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 19
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 20
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 21
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 22
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 23
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 24
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 25
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 26
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 27
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 28
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 29
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 30
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 31
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 32
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 33
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 34
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 35
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 36
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 37
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 38
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:52:28+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:52 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-client-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 39
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-client-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-04-04T06:57:08+00:00
INFO Kubelet serving certificate has expired, waiting for automatic renewal... [will take up to 8 minutes]
DEBU retry loop: attempt 0
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 1
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 2
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 3
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 4
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 5
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 6
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 7
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 8
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 9
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 10
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 11
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 12
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:55:09+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:55 +0000
DEBU error: Temporary error: certificate /var/lib/kubelet/pki/kubelet-server-current.pem still expired - sleeping 5s
DEBU retry loop: attempt 13
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /var/lib/kubelet/pki/kubelet-server-current.pem -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-04-04T06:57:08+00:00
DEBU Waiting for apiserver availability
DEBU retry loop: attempt 0
DEBU About to run SSH command:
oc get nodes --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: NAME                 STATUS   ROLES           AGE   VERSION
crc-ctj2r-master-0   Ready    master,worker   37d   v1.19.0+1833054
DEBU NAME                 STATUS   ROLES           AGE   VERSION
crc-ctj2r-master-0   Ready    master,worker   37d   v1.19.0+1833054
DEBU Waiting for availability of resource type 'secret'
DEBU retry loop: attempt 0
DEBU About to run SSH command:
oc get secret --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: NAME                       TYPE                                  DATA   AGE
builder-dockercfg-67pbn    kubernetes.io/dockercfg               1      37d
builder-token-7dpgv        kubernetes.io/service-account-token   4      37d
builder-token-crhrm        kubernetes.io/service-account-token   4      37d
default-dockercfg-qlhc5    kubernetes.io/dockercfg               1      37d
default-token-4bcxf        kubernetes.io/service-account-token   4      37d
default-token-66jc2        kubernetes.io/service-account-token   4      37d
deployer-dockercfg-7gpfr   kubernetes.io/dockercfg               1      37d
deployer-token-2xkxq       kubernetes.io/service-account-token   4      37d
deployer-token-vpvdw       kubernetes.io/service-account-token   4      37d
DEBU NAME                       TYPE                                  DATA   AGE
builder-dockercfg-67pbn    kubernetes.io/dockercfg               1      37d
builder-token-7dpgv        kubernetes.io/service-account-token   4      37d
builder-token-crhrm        kubernetes.io/service-account-token   4      37d
default-dockercfg-qlhc5    kubernetes.io/dockercfg               1      37d
default-token-4bcxf        kubernetes.io/service-account-token   4      37d
default-token-66jc2        kubernetes.io/service-account-token   4      37d
deployer-dockercfg-7gpfr   kubernetes.io/dockercfg               1      37d
deployer-token-2xkxq       kubernetes.io/service-account-token   4      37d
deployer-token-vpvdw       kubernetes.io/service-account-token   4      37d
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
INFO Adding user's pull secret to the cluster ...
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU Waiting for availability of resource type 'clusterversion'
DEBU retry loop: attempt 0
DEBU About to run SSH command:
oc get clusterversion --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: NAME      VERSION   AVAILABLE   PROGRESSING   SINCE   STATUS
version   4.6.15    True        False         37d     Error while reconciling 4.6.15: the cluster operator monitoring is degraded
DEBU NAME      VERSION   AVAILABLE   PROGRESSING   SINCE   STATUS
version   4.6.15    True        False         37d     Error while reconciling 4.6.15: the cluster operator monitoring is degraded
DEBU About to run SSH command:
oc get clusterversion version -o jsonpath="{['spec']['clusterID']}" --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output:
INFO Updating cluster ID ...
DEBU About to run SSH command:
oc patch clusterversion version -p '{"spec":{"clusterID":"20ce658c-79b7-4592-a465-18a0779f8b4b"}}' --type merge --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: clusterversion.config.openshift.io/version patched
DEBU Waiting for the renewal of the request header client ca...
DEBU retry loop: attempt 0
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 1
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 2
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 3
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 4
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 5
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 6
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 7
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 8
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 9
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 10
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 11
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 12
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 13
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 14
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 15
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 16
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 17
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 18
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 19
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 20
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 21
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 22
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 23
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 24
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 25
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 26
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 27
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 28
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 29
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 30
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 31
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 32
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-03-05T06:58:21+00:00
DEBU Certs have expired, they were valid till: 05 Mar 21 06:58 +0000
DEBU error: Temporary error: certificate still expired - sleeping 2s
DEBU retry loop: attempt 33
DEBU About to run SSH command:
date --date="$(sudo openssl x509 -in /etc/kubernetes/static-pod-resources/kube-apiserver-certs/configmaps/aggregator-client-ca/ca-bundle.crt -noout -enddate | cut -d= -f 2)" --iso-8601=seconds
DEBU SSH command results: err: <nil>, output: 2021-04-10T20:18:06+00:00
DEBU Waiting for availability of resource type 'pod'
DEBU retry loop: attempt 0
DEBU About to run SSH command:
oc get pod --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output:
DEBU
DEBU retry loop: attempt 0
DEBU About to run SSH command:
oc delete pod --all -n openshift-apiserver --context admin --cluster crc --kubeconfig /opt/kubeconfig
DEBU SSH command results: err: <nil>, output: pod "apiserver-bc6c767b-mlxhj" deleted
INFO Starting OpenShift cluster ... [waiting 3m]
INFO Updating kubeconfig
DEBU retry loop: attempt 0
DEBU About to run SSH command with hidden output
DEBU SSH command failed
DEBU error: Temporary error: ssh command error:
command : oc get co -ojson --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 2s
DEBU retry loop: attempt 1
DEBU About to run SSH command with hidden output
DEBU SSH command failed
DEBU error: Temporary error: ssh command error:
command : oc get co -ojson --context admin --cluster crc --kubeconfig /opt/kubeconfig
err     : Process exited with status 1\n - sleeping 2s
DEBU retry loop: attempt 2
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 3
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 4
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 5
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 6
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 7
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 8
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 9
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 10
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 11
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 12
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 13
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 14
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 15
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 16
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 17
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 18
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
thVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 19
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU retry loop: attempt 20
DEBU About to run SSH command with hidden output
DEBU SSH command succeeded
DEBU authentication operator is still progressing, Reason: OAuthVersionRoute_WaitingForRoute
DEBU authentication operator not available, Reason: OAuthRouteCheckEndpointAccessibleController_EndpointUnavailable::OAuthVersionRoute_RequestFailed
DEBU error: Temporary error: cluster operator authentication not ready - sleeping 2s
DEBU RetryAfter timeout after 21 tries
WARN Skipping the kubeconfig update. Cluster operator authentication still not ready after 2min.
WARN The cluster might report a degraded or error state. This is expected since several operators have been disabled to lower the resource usage. For more information, please consult the documentation
Started the OpenShift cluster

To access the cluster, first set up your environment by following the instructions returned by executing 'crc oc-env'.
Then you can access your cluster by running 'oc login -u developer -p developer https://api.crc.testing:6443'.
To login as a cluster admin, run 'oc login -u kubeadmin -p APBEh-jjrVy-hLQZX-VI9Kg https://api.crc.testing:6443'.

You can also run 'crc console' and use the above credentials to access the OpenShift web console.
The console will open in your default browser.
PS C:\Users\Jeipi> crc console
Opening the OpenShift Web Console in the default browser...
```

`Version crc 1.23.1`

```
PS C:\Users\Jeipi> crc setup --log-level debug
DEBU CodeReady Containers version: 1.23.1+be17b141
DEBU OpenShift version: 4.7.0 (embedded in executable)
DEBU Running 'crc setup'
CodeReady Containers is constantly improving and we would like to know more about usage (more details at https://developers.redhat.com/article/tool-data-collection)
Your preference can be changed manually if desired using 'crc config set consent-telemetry <yes/no>'
Would you like to contribute anonymous usage statistics? [y/N]: n
No worry, you can still enable telemetry manually with the command 'crc config set consent-telemetry yes'.
INFO Checking if podman remote executable is cached
DEBU Currently podman remote is not supported
INFO Checking if admin-helper executable is cached
DEBU admin-helper executable is not cached
INFO Caching admin-helper executable
DEBU Trying to extract admin-helper-windows.exe from crc executable
DEBU Copying 'C:\Users\Jeipi\AppData\Local\Temp\crc807212710\admin-helper-windows.exe' to 'C:\Users\Jeipi\.crc\bin\admin-helper-windows.exe'
DEBU admin-helper executable cached
INFO Checking minimum RAM requirements
DEBU Total memory of system is 34195279872 bytes
INFO Checking if running in a shell with administrator rights
INFO Checking Windows 10 release
INFO Checking Windows edition
DEBU Running on Windows ProfessionalEducation edition
INFO Checking if Hyper-V is installed and operational
INFO Checking if user is a member of the Hyper-V Administrators group
INFO Checking if Hyper-V service is enabled
INFO Checking if the Hyper-V virtual switch exist
INFO Found Virtual Switch to use: crc
INFO Checking if CRC bundle is extracted in '$HOME/.crc'
INFO Checking if C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0.crcbundle exists
DEBU error getting bundle info for crc_hyperv_4.7.0.crcbundle: could not find cached bundle info in C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0: CreateFile C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0: The system cannot find the path specified.
DEBU could not find cached bundle info in C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0: CreateFile C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0: The system cannot find the path specified.
INFO Extracting bundle from the CRC executable
DEBU Error changing C:\Users\Jeipi\.crc\cache permissions to 0775
INFO Ensuring directory C:\Users\Jeipi\.crc\cache exists
INFO Extracting embedded bundle crc_hyperv_4.7.0.crcbundle to C:\Users\Jeipi\.crc\cache
DEBU Extracting embedded 'crc_hyperv_4.7.0.crcbundle' from C:\Users\Jeipi\Documents\crc-windows-1.23.1-amd64\crc.exe to C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0.crcbundle
INFO Uncompressing crc_hyperv_4.7.0.crcbundle
DEBU Uncompressing C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0.crcbundle to C:\Users\Jeipi\.crc\cache\tmp-extract
crc.vhdx: 11.41 GiB / 11.41 GiB [-------------------------------------------------------------------------------------------------------------------------------------------------------------------] 100.00%
DEBU Copying 'C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0\oc.exe' to 'C:\Users\Jeipi\.crc\bin\oc\oc.exe'
Setup is complete, you can now run 'crc start' to start the OpenShift cluster
PS C:\Users\Jeipi> crc start -p C:\Users\Jeipi\Documents\crc-windows-1.23.1-amd64\pull-secret.txt --log-level debug
DEBU CodeReady Containers version: 1.23.1+be17b141
DEBU OpenShift version: 4.7.0 (embedded in executable)
DEBU Running 'crc start'
DEBU Total memory of system is 34195279872 bytes
DEBU Copying 'C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0\oc.exe' to 'C:\Users\Jeipi\.crc\bin\oc\oc.exe'
DEBU No new version available. The latest version is 1.23.1
INFO Checking if podman remote executable is cached
DEBU Currently podman remote is not supported
INFO Checking if admin-helper executable is cached
DEBU Running 'C:\Users\Jeipi\.crc\bin\admin-helper-windows.exe --version'
DEBU Found admin-helper-windows.exe version 0.0.2
DEBU admin-helper executable already cached
INFO Checking minimum RAM requirements
DEBU Total memory of system is 34195279872 bytes
INFO Checking if running in a shell with administrator rights
INFO Checking Windows 10 release
INFO Checking Windows edition
DEBU Running on Windows ProfessionalEducation edition
INFO Checking if Hyper-V is installed and operational
INFO Checking if user is a member of the Hyper-V Administrators group
INFO Checking if Hyper-V service is enabled
INFO Checking if the Hyper-V virtual switch exist
INFO Found Virtual Switch to use: crc
DEBU Checking file: C:\Users\Jeipi\.crc\machines\crc\.crc-exist
DEBU Using secret from configuration
DEBU Copying 'C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0\oc.exe' to 'C:\Users\Jeipi\.crc\bin\oc\oc.exe'
INFO Loading bundle: crc_hyperv_4.7.0.crcbundle ...
INFO Creating CodeReady Containers VM for OpenShift 4.7.0...
DEBU Running pre-create checks...
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive @(Get-Module -ListAvailable hyper-v).Name | Get-Unique
                   ] : Hyper-V
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive @([Security.Principal.WindowsPrincipal][Security.Principal.WindowsIdentity]::GetCurrent()).IsInRole(([System.Security.Principal.SecurityIdentifier]::new("S-1-5-32-578")))
                       True
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive [Console]::OutputEncoding = [Text.Encoding]::UTF8; (Hyper-V\Get-VMSwitch).Name
DEBU [stdout =====>] : Default Switch

DEBU [stderr =====>] :
DEBU Creating machine...                                                                                                                                                                                      DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive [Console]::OutputEncoding = [Text.Encoding]::UTF8; (Hyper-V\Get-VMSwitch).Name                    DEBU [stdout =====>] : Default Switch                                                                                                                                                                                                                                                                                                                                                                                       DEBU [stderr =====>] :                                                                                                                                                                                        DEBU Using switch "crc"
DEBU Creating VM...
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\New-VM crc -Path 'C:\Users\Jeipi\.crc\machines\crc' -MemoryStartupBytes 9216MB -SwitchName 'crc'
DEBU [stdout =====>] :
Name State CPUUsage(%) MemoryAssigned(M) Uptime   Status             Version
---- ----- ----------- ----------------- ------   ------             -------
crc  Off   0           0                 00:00:00 Operating normally 9.0


DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Set-VMMemory -VMName crc -DynamicMemoryEnabled $false
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Set-VMProcessor crc -Count 4
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Add-VMHardDiskDrive -VMName crc -Path 'C:\Users\Jeipi\.crc\machines\crc\crc.vhdx'
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU Starting VM...
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive Hyper-V\Start-VM crc
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU Waiting for host to start...
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
DEBU [stdout =====>] :
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
 EBU [stdout =====>] : fe80::695b:7182:5897:4527
DEBU [stderr =====>] :
DEBU Waiting for machine to be running, this may take a few minutes...
DEBU retry loop: attempt 0
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU Machine is up and running!
DEBU Machine successfully created
DEBU Created C:\Users\Jeipi\.crc\machines\crc\.crc-exist
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive ( Hyper-V\Get-VM crc ).state
                   ] : Running
DEBU [stderr =====>] :
DEBU [executing ==>] : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -NoProfile -NonInteractive (( Hyper-V\Get-VM crc ).networkadapters[0]).ipaddresses[0]
              ====>] : 192.168.8.52
DEBU [stderr =====>] :
DEBU Waiting until ssh is available
DEBU retry loop: attempt 0
DEBU Running SSH command: exit 0
DEBU Using ssh private keys: [C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0\id_ecdsa_crc]
DEBU SSH command results: err: <nil>, output:
INFO CodeReady Containers VM is running
INFO Generating new SSH Key pair ...
DEBU Running SSH command: cat /home/core/.ssh/authorized_keys
DEBU SSH command results: err: <nil>, output: ecdsa-sha2-nistp521 AAAAE2VjZHNhLXNoYTItbmlzdHA1MjEAAAAIbmlzdHA1MjEAAACFBAEown0B3bgXkVFCqYIY2+1HfVCSaRTP+LSgUa/bzPfs8O+5dkaR0gj5PlpISX8fyTPGzxbMCvHNsaRYa0sPNNFbXQE0cd/onR17Jhk6aVxMPyFtjC2jrbXIBoA+4wpV2yqP3RuAk3TBGH4iWn4wP/hcuL/PWQ5Wt8tzuLFkv/pmeJOLBw== core
INFO Updating authorized keys ...
DEBU Running SSH command: echo 'ecdsa-sha2-nistp521 AAAAE2VjZHNhLXNoYTItbmlzdHA1MjEAAAAIbmlzdHA1MjEAAACFBABpOjYIjLC5NVtVlgyyDmYFMfxiBSvjCcP59pwphDmGhekghm5LOXGexIZyoZhobs6Ms777erEIhxIt+c/sej6jCQHiwtstTIDWotKFg50/n1YjSfmDDgtFNeU6oTIzHSFZ0bJUMxBoDYdpM9cYYaihoF9dE3AzsU6pFqnabv45JInPFw==
' > /home/core/.ssh/authorized_keys; chmod 644 /home/core/.ssh/authorized_keys
DEBU SSH command results: err: <nil>, output:
INFO Copying kubeconfig file to instance dir ...
DEBU Copying 'C:\Users\Jeipi\.crc\cache\crc_hyperv_4.7.0\kubeconfig' to 'C:\Users\Jeipi\.crc\machines\crc\kubeconfig'
DEBU Running SSH command: sudo xfs_growfs / >/dev/null
DEBU SSH command results: err: <nil>, output:
INFO Starting network time synchronization in CodeReady Containers VM
DEBU Running SSH command: sudo timedatectl set-ntp on
DEBU SSH command results: err: <nil>, output:
DEBU Creating /var/srv/dnsmasq.conf with permissions 0644 in the CRC VM
DEBU Running private SSH command
DEBU SSH command succeeded
DEBU Running SSH command: sudo podman rm -f dnsmasq
DEBU SSH command results: err: Process exited with status 1, output:
DEBU Running SSH command: sudo rm -f /var/lib/cni/networks/podman/10.88.0.8
DEBU SSH command results: err: <nil>, output:
DEBU Running SSH command: sudo podman run  --ip 10.88.0.8 --name dnsmasq -v /var/srv/dnsmasq.conf:/etc/dnsmasq.conf -p 53:53/udp --privileged -d quay.io/crcont/dnsmasq:latest
DEBU SSH command results: err: <nil>, output: 1d894e63693679bca1c80681367f8d873d6138f0e59a22a03c477ff2c1c21efc
DEBU Running SSH command: cat /etc/resolv.conf
DEBU SSH command results: err: <nil>, output: # Generated by NetworkManager
search lan
nameserver 192.168.8.1
nameserver 2001::1
DEBU Creating /etc/resolv.conf with permissions 0644 in the CRC VM
DEBU Running private SSH command
DEBU SSH command succeeded
DEBU retry loop: attempt 0
DEBU Running SSH command: host -R 3 foo.apps-crc.testing
DEBU SSH command results: err: <nil>, output: foo.apps-crc.testing has address 192.168.8.52
INFO Check internal and public DNS query ...
DEBU Running SSH command: host -R 3 quay.io
DEBU SSH command results: err: <nil>, output: quay.io has address 18.210.212.75
quay.io has address 3.233.133.41
quay.io has address 50.16.140.223
quay.io has address 3.213.173.170
quay.io has address 34.197.63.98
quay.io has address 52.72.182.67
quay.io mail is handled by 30 aspmx2.googlemail.com.
quay.io mail is handled by 10 aspmx.l.google.com.                                                                                                                                                             quay.io mail is handled by 20 alt1.aspmx.l.google.com.                                                                                                                                                        quay.io mail is handled by 20 alt2.aspmx.l.google.com.                                                                                                                                                        INFO Check DNS query from host ...                                                                                                                                                                            Failed to query DNS from host: lookup api.crc.testing: no such host                                                                                                                                           PS C:\Users\Jeipi> crc start
INFO A CodeReady Containers VM for OpenShift 4.7.0 is already running
Started the OpenShift cluster.

The server is accessible via web console at:
  https://console-openshift-console.apps-crc.testing

Log in as administrator:
  Username: kubeadmin
  Password: T3sJD-jjueE-2BnHe-ftNBw                                                                                                                                                                                                                                                                                                                                                                                         Log in as user:                                                                                                                                                                                                 Username: developer                                                                                                                                                                                           Password: developer                                                                                                                                                                                         
Use the 'oc' command line interface:
  PS> & crc oc-env | Invoke-Expression
  PS> oc login -u developer https://api.crc.testing:6443
PS C:\Users\Jeipi> crc console
Opening the OpenShift Web Console in the default browser...
PS C:\Users\Jeipi> crc stop
INFO Stopping the OpenShift cluster, this may take a few minutes...
Stopped the OpenShift cluster
PS C:\Users\Jeipi> crc start
INFO Checking if podman remote executable is cached
INFO Checking if admin-helper executable is cached
INFO Checking minimum RAM requirements
INFO Checking if running in a shell with administrator rights
INFO Checking Windows 10 release
INFO Checking Windows edition
INFO Checking if Hyper-V is installed and operational
INFO Checking if user is a member of the Hyper-V Administrators group
INFO Checking if Hyper-V service is enabled
INFO Checking if the Hyper-V virtual switch exist
INFO Found Virtual Switch to use: crc
INFO Starting CodeReady Containers VM for OpenShift 4.7.0...
INFO CodeReady Containers VM is running
INFO Starting network time synchronization in CodeReady Containers VM
INFO Will run as admin: add dns server address to interface vEthernet (crc)
INFO Check internal and public DNS query ...
INFO Check DNS query from host ...
INFO Adding user's pull secret to instance disk...
CodeReady Containers requires a pull secret to download content from Red Hat.
You can copy it from the Pull Secret section of https://cloud.redhat.com/openshift/create/local.
? Please enter the pull secret *******************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************INFO Verifying validity of the kubelet certificates ... ***************************************************************
INFO Starting OpenShift kubelet service
INFO Waiting for kube-apiserver availability... [takes around 2min]
INFO Adding user's pull secret to the cluster ...
INFO Updating cluster ID ...
INFO Starting OpenShift cluster ... [waiting for the cluster to stabilize]
INFO 6 operators are progressing: dns, image-registry, network, openshift-controller-manager, operator-lifecycle-manager-packageserver, service-ca
INFO Operator kube-apiserver is progressing
INFO 2 operators are progressing: kube-apiserver, operator-lifecycle-manager-packageserver
INFO Operator kube-apiserver is progressing
INFO All operators are available. Ensuring stability ...
INFO Operators are stable (2/3) ...
INFO Operators are stable (3/3) ...
INFO Updating kubeconfig
WARN The cluster might report a degraded or error state. This is expected since several operators have been disabled to lower the resource usage. For more information, please consult the documentation
Started the OpenShift cluster.

The server is accessible via web console at:
  https://console-openshift-console.apps-crc.testing

Log in as administrator:
  Username: kubeadmin
  Password: T3sJD-jjueE-2BnHe-ftNBw

Log in as user:
  Username: developer
  Password: developer

Use the 'oc' command line interface:
  PS> & crc oc-env | Invoke-Expression
  PS> oc login -u developer https://api.crc.testing:6443
PS C:\Users\Jeipi>
PS C:\Users\Jeipi>
PS C:\Users\Jeipi>
PS C:\Users\Jeipi> crc console
Opening the OpenShift Web Console in the default browser...
PS C:\Users\Jeipi> crc oc-env
$Env:PATH = "C:\Users\Jeipi\.crc\bin\oc;$Env:PATH"
# Run this command to configure your shell:
# & crc oc-env | Invoke-Expression
```