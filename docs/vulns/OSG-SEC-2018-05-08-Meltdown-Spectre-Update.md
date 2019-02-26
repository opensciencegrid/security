# OSG-SEC-2018-01-04 CPU hardware vulnerabilities 

## [UPDATE 2018-05-08]

Dear OSG Security Contacts,

This is an update of the security announcement about the CPU hardware in modern processors that were reported in the beginning of January and are widely known as Meltdown and Spectre and described in CVE-2017-5754 [[1]](#more-information).  An updated kernel is now available for Red Hat Enterprise Linux 7 that fixes another aspect of those issues, and also fixes many other security issues.  The OSG Security team considers applying this update to be IMPORTANT.

## AFFECTED VERSIONS:
EL7 kernel versions prior to 3.10-0-862 are affected.

## WHAT YOU SHOULD DO:
Update the kernel using the following command: 

    yum update kernel

Kernel updates are available for the following systems. 
 - Red Hat Enterprise Linux 7 [2]
 - Scientific Linux 7 [3] 
 - CentOS 7 (in the “cr” yum repo - - use “yum --enablerepo=cr update kernel”) 

This should update the kernel to version 3.10.0-862.el7.  The system must be rebooted for this update to take effect.

NOTE: this kernel is known to cause problems with ZFS [4]; machines that support ZFS should wait for an updated ZFS release.

## RELATED LINKS:
 - https://ticket.opensciencegrid.org/35754

## REFERENCES:
* [1] https://access.redhat.com/security/cve/cve-2017-5754
* [2] https://access.redhat.com/errata/RHSA-2018:1062 
* [3] https://www.scientificlinux.org/category/sl-errata/slsa-20181062-1/ 
* [4] https://github.com/zfsonlinux/zfs/issues/7460

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team

