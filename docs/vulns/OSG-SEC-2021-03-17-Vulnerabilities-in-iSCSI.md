# OSG-SEC-2021-03-17 vulnerabilities in iSCSI 

Dear OSG Security Contacts,

## UPDATE:
Updates are now available for RHEL 7/8 and CentOS 7/8. The OSG Security team recommends applying these updates, especially if the mitigation steps recommended previously have not been implemented.

## ORIGINAL ANNOUNCEMENT:
There are three new vulnerabilities in the iSCSI kernel subsystem described in CVE-2021-27363 [1], CVE-2021-27364 [2] and CVE-2021-27365 [3] that could allow local privilege escalation to root. 

The OSG Security team considers these vulnerabilities to be of HIGH severity and highly recommend patching your Linux kernel once the updates are available; in the meantime, a mitigation is available and we recommend applying this mitigation if possible.

## IMPACTED VERSIONS:
RedHat-based distributions (RHEL 7, 8, and derivatives) which were installed with GUI, Workstation, or Virtualization Host
Debian-based distributions with iSCSI hardware or manual iSCSI setups

## WHAT ARE THE VULNERABILITIES:
A flaw was found in the Linux kernel. A heap buffer overflow in the iSCSI subsystem is triggered by setting an iSCSI string attribute to a value larger than one page and then trying to read it. [3]  These three vulnerabilities can lead to local elevation of privileges, information leaks, and denials of service.

## WHAT YOU SHOULD DO:
At present, no updates are available for RHEL 7, 8 or their derivatives. The OSG Security team recommends sites carry out the following mitigation on hosts to which users have shell access, including worker nodes and submit hosts.

The libiscsi module will be auto-loaded when required, its use can be disabled by preventing the module from loading with the following instructions:

```
# echo "install libiscsi /bin/true" >> /etc/modprobe.d/disable-libiscsi.conf
```

The system will need to be restarted if the libiscsi modules are loaded. In most circumstances, the libiscsi kernel modules will be unable to be unloaded while any network interfaces are active and the protocol is in use. [3]

If the system requires iSCSI to work correctly, this mitigation may not be suitable.

## REFERENCES
[1] https://access.redhat.com/security/cve/CVE-2021-27363 

[2] https://access.redhat.com/security/cve/CVE-2021-27364 

[3] https://access.redhat.com/security/cve/CVE-2021-27365  


Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
