# OSG-SEC-2018-05-18 Multiple EL7 Linux kernel vulnerabilities

Dear OSG Security Contacts,

A new kernel is available for RHEL7 and its derivatives that patches multiple vulnerabilities.  These include one for unprivileged user namespaces that OSG security previously announced, one that can be used for privilege escalation on KVM virtual machines, and one that can enable an unprivileged user on any machine to cause it to crash. OSG security considers patching these vulnerabilities to be IMPORTANT.

## IMPACTED VERSIONS:
Red Hat Enterprise Linux 7 and its derivatives.

## WHAT ARE THE VULNERABILITIES:
 - The 'use-after-free' vulnerability flaw in XFRM mentioned in a previous announcement (OSG-SEC-2017-12-19) can lead to privilege escalation on systems that have enabled unprivileged user namespaces, if not mitigated by disabling network namespaces [1].
 - A  vulnerability concerning the Linux kernel's KVM hypervisor exception handling can allow an unprivileged guest VM user to crash the guest or, potentially, escalate their privileges in the guest [2].
- A vulnerability in the Linux kernel exception handling can allow an unprivileged user to crash the system and cause a Denial of Service (DoS) [3].

## WHAT YOU SHOULD DO:
Upgrade the kernel to version 3.10.0-862.2.3. This is available now in the Scientific Linux 7 "sl-security" yum repository and is also available in the CentOS 7 "cr" yum repository. Reboot after upgrading. If you had disabled network namespaces as described in the OSG singularity install instructions [4], you may re-enable them.

## RELATED LINKS:
- https://ticket.grid.iu.edu/37880

## REFERENCES
- [1] https://access.redhat.com/security/cve/cve-2017-16939
- [2] https://access.redhat.com/security/cve/cve-2018-1087
- [3] https://access.redhat.com/security/cve/cve-2018-8897
- [4] https://opensciencegrid.org/docs/worker-node/install-singularity/#enabling-singularity-via-oasis

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
