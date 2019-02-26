# OSG-SEC-2018-04-30 Multiple Singularity Vulnerabilities

Dear OSG Security Contacts,

Multiple vulnerabilities have been publicly reported concerning setuid-root installations of Singularity, including more than one way for a user outside of a container to escalate privileges.  OSG security considers this a Critical vulnerability and the impact is high for our infrastructure.  A new version is available in the osg-development yum repository and it is planned to be released to the osg yum repository in the morning on Tuesday, May 1.

## IMPACTED VERSIONS:
Singularity versions 2.4.6 and earlier are impacted.  Both EL6 and EL7 based systems are impacted.  Installations using unprivileged singularity [1] on EL7 are not affected by these issues.

## WHAT ARE THE VULNERABILITIES:
Unprivileged users who have access to run setuid-root singularity can:

- create world writable files in root-owned directories on the host system
- create folders outside of the container
- bypass the “enable overlay = no” option in singularity.conf (EL7 only)
- exploit buffer overflows

For more details see the singularity-2.5.0 release announcement [2]. Note especially that jobs running inside of singularity containers are not able to exploit these vulnerabilities.

## WHAT YOU SHOULD DO:
IMMEDIATELY begin testing the latest singularity version with the following command:

- yum update --enablerepo=osg-development singularity-runtime

Version 2.5.0-1.1.osg34 includes a pending pull request [3], and there is one more potential known issue at this time [4] but it is not known to affect OSG use cases.  

Report any problems seen to security@opensciencegrid.org.  If no problems are seen with your use cases you may upgrade before the release to the osg yum repository.

## RELATED LINKS
- http://opensciencegrid.github.io/docs/worker-node/install-singularity/ - OSG singularity install documentation.
- https://ticket.grid.iu.edu/37322

## REFERENCES
- [1] http://opensciencegrid.github.io/docs/worker-node/install-singularity/#unprivileged-singularity
- [2] https://github.com/singularityware/singularity/releases/tag/2.5.0
- [3] https://github.com/singularityware/singularity/pull/1491
- [4] https://github.com/singularityware/singularity/pull/1490

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
