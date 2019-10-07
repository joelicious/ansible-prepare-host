Prepare a host for OpenShift 4 Provisioning
-------------------------------------------

The intent of these instructions is to install
RHEL on decently sized bare metal so that it can
perform as a KVM host.

OpenShift 4 has significant requirements for 
individual nodes, so these instructions make 
it possible to install VMs to meet the needs
of the installer.

For the purposes of these ansible playbook, RHEL8
is obtained and provisioned on the bare metal
host.

After completing the insall, add <username> to
the sudoers list for the convience of future
commands.

To add <username> to sudoers list:

``` 
su
usermod -aG wheel <username>
su <username>
```

Then enable sshd so that ansible can access the host.

```
sudo systemctl start sshd.service
sudo systemctl enable sshd.service
```


