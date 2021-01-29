## UPDATE:
CentOS8 packages now available [6].

## CORRECTION:
In the previous notice the patched versions were erroneously listed as the impacted versions. The heading has been updated in the message below for clarity.

----------
Dear OSG Security Contacts,

A heap-based buffer overflow vulnerability that could lead to privilege escalation described in CVE-2021-3156 [1] has been discovered in 'sudo' [2]. The vulnerable code was introduced in July 2011 and affects all legacy versions of sudo from v1.8.2 to v1.8.31p2, and all stable versions from v1.9.0 to v1.9.5p1, using default configurations. The OSG Security team considers this vulnerability to be of CRITICAL severity.

Patched Versions:

RHEL/CentOS7: sudo-1.8.23-10.el7_9.1 [3][4]

RHEL/CentOS8: sudo-1.8.29-6.el8_3.1 [5]

Other operating systems and distributions are also likely to be exploitable.

## WHAT ARE THE VULNERABILITIES:
The vulnerability is exploitable by any local user. The attacker does not need to know the user's password, nor be a part of any sudoers list. Successful exploitation of this vulnerability could lead to privilege escalation.

## WHAT YOU SHOULD DO:
How to Check: As a non-root user account, run the following:
```sudoedit -s '\' `perl -e 'print "A" x 65536'` ```

A vulnerable system will segfault or show a similar error indicating memory corruption.

If your system has local user accounts, update to the latest version of 'sudo' available for your operating system. After updating, run the command in "How to Check" above to verify the patch. If a patch is not yet available for your system, a mitigation using 'systemtap' has been described in the RedHat announcement for this issue [2]. The OSG Security team recommends updating as soon as possible.

## RELATED LINKS
https://wiki.egi.eu/wiki/SVG:Advisory-SVG-CVE-2021-3156

https://ubuntu.com/security/CVE-2021-3156

https://security-tracker.debian.org/tracker/CVE-2021-3156

http://mirror.centos.org/centos-8/8/BaseOS/x86_64/os/Packages/?C=M;O=D

## REFERENCES
[1] https://access.redhat.com/security/cve/CVE-2021-3156

[2] https://blog.qualys.com/vulnerabilities-research/2021/01/26/cve-2021-3156-heap-based-buffer-overflow-in-sudo-baron-samedit

[3] https://access.redhat.com/errata/RHSA-2021:0221

[4] https://lists.centos.org/pipermail/centos-announce/2021-January/048252.html

[5] https://access.redhat.com/errata/RHSA-2021:0218 (RHEL8)

[6] http://mirror.centos.org/centos-8/8/BaseOS/x86_64/os/Packages/?C=M;O=D


Please contact the OSG security team immediately at security at opensciencegrid.org if you have any questions or concerns.

OSG Security Team
