# OSG-SEC-2018-07-05 Singularity Vulnerabilities

Dear OSG Security Contacts,

High-severity vulnerabilities have been publicly reported concerning installations of singularity that support overlayfs, which is the default on EL7.  If overlay is available, a malicious user could exploit this vulnerability to escalate privileges.  OSG security considers this a Critical vulnerability and the impact is high for our infrastructure.  A new version is available in the osg-testing repository and is planned to be released to the osg repository on Friday, July 6, after more extensive testing.  A workaround not requiring an upgrade is outlined below.

## IMPACTED VERSIONS:
EL7 based systems with singularity versions 2.5.1 and earlier with a default configuration are impacted.  EL6 is not affected.

## WHAT ARE THE VULNERABILITIES:
A vulnerability with the singularity mount command enables read access to protected files.  In addition, a race condition allows read access to protected files in the root filesystem with other singularity commands. These can lead to privilege escalation.

For more details see the singularity-2.5.2 release announcement [1].  Jobs running inside of singularity containers are not able to exploit these vulnerabilities. 

## WHAT YOU SHOULD DO:
On EL7 systems, one of the following actions should be applied IMMEDIATELY:
1. Configure the following workaround: set ‘enable overlay = no’ in /etc/singularity/singularity.conf.  No OSG VO using singularity in production currently requires this feature.  (This may already be disabled because of a workaround for a previous announced vulnerability [2], which was later fixed.)
2. Begin testing the latest singularity version 2.5.2-1.osg34 with the following command `yum update --enablerepo=osg-testing singularity-runtime` and if it works for your workflows, install it on all nodes.
 
Report any problems seen to security@opensciencegrid.org.  If no problems are seen with your use cases you may upgrade before the release to the osg yum repository.

## REFERENCES
[1] https://github.com/singularityware/singularity/releases/tag/2.5.2
[2] OSG-SEC-2018-04-30
[3] https://cve.mitre.org/cgi-bin/cvename.cgi?name=2018-12021

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team

