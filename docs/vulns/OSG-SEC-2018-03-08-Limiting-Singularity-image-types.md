# OSG-SEC-2018-03-08 Limiting Singularity image types

Dear OSG Security Contacts,

This security advisory is INFORMATIONAL for OSG sites that have installed Singularity. The OSG Security Team would like to inform sites of how they can reduce risk of unknown exploits by disabling unused features.

The default configuration of Singularity allows image types that carry a higher theoretical risk of attack. These image types are not currently used on the OSG, no specific exploit has been found, and we believe that any discovered vulnerability would be patched by RedHat. For those reasons, sites may choose whether or not to protect against the potential vulnerability. This issue has been documented in the OSG singularity install documentation for a few months so you may already be aware of it, but there has been no OSG security announcement about it before now.

## IMPACTED VERSIONS:
- RedHat 6 & 7 and its derivatives are affected, and all versions of Singularity.

## WHAT IS THE POTENTIAL VULNERABILITY:
By default the setuid (RPM) distribution of Singularity allows unprivileged users to mount image files via loopback devices. This carries an inherently higher exposure to potential kernel exploits, as discussed in [1]. There are no known public exploits at this time, but Linux kernel developers are concerned enough to refuse allowing the capability in the kernel. Singularity enables the capability via a setuid-root function.

No OSG VOs require mounting image files via loopback devices with Singularity on worker nodes. They instead use operating system images in directory trees distributed in CVMFS.  However, as sites utilize OSG-provided Singularity for non-OSG use cases, we have not changed the upstream default value. Changing the RPM’s default values could potentially cause problems when upgrading between Singularity versions.

Sites should balance their understanding of the elevated risk with local use cases when planning any configuration change.

## WHAT YOU SHOULD DO:
Read the “Limiting Image Types” section in the OSG documentation for installing Singularity [2] and decide whether or not to set the number of loopback devices to zero. Note the warning about watching out for singularity.conf.rpmnew after upgrades.

Sites should also consider limiting their vulnerability further by installing only the singularity-runtime rpm and not the singularity rpm on worker nodes.

## RELATED LINKS:
- https://ticket.grid.iu.edu/36388

## REFERENCES:
- [1] https://lwn.net/Articles/652468/
- [2] http://opensciencegrid.github.io/docs/worker-node/install-singularity/#limiting-image-types

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
