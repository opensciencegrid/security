# OSG-SEC-2020-05-05 Singularity and unprivileged user namespaces

Dear OSG Security Contacts,

Red Hat Enterprise Linux 7 supports a kernel feature called unprivileged user namespaces that enables singularity to run completely unprivileged.  All OSG VOs (including WLCG VOs) that use singularity are now configured to run singularity unprivileged out of CVMFS when they can.  OSG security believes this to be a significantly lower risk than having singularity installed with setuid root enabled.  We recommend that sites enable unprivileged user namespaces on their RHEL 7 worker nodes if they haven’t, and remove singularity rpms if there is no non-OSG requirement to keep them.

## IMPACTED VERSIONS:

RHEL 7.6 and later are affected.
RHEL 8 has unprivileged user namespaces enabled by default.
RHEL 6 cannot enable unprivileged user namespaces.

## WHAT ARE THE VULNERABILITIES:

There are no known current exploits with setuid root singularity, but there have been in the past.  Setuid root programs are notoriously difficult to secure, and there are likely to be more exploits discovered in the future.

## WHAT YOU SHOULD DO:

On RHEL 7 worker nodes, enable unprivileged user namespaces by following the instructions on the OSG singularity installation page [1].  Then, if you have no requirement to keep the rpm installed for non-OSG purposes, remove singularity rpms from your worker nodes.  If your singularity installation is version 2, instead remove singularity-runtime rpms.  If you have to keep the singularity rpm installed, consider setting the configuration ‘allow setuid = no’.  More information on making that choice is available [2].

Note that if there were local changes to singularity.conf, VOs will no longer be using them.  Extra local bind paths can be added to jobs through the SINGULARITY_BINDPATH environment variable.

## REFERENCES

[1]­­­⁣⁣⁣ https://opensciencegrid.org/docs/worker-node/install-singularity/#enabling-unprivileged-singularity
[2]­­­⁣⁣⁣ https://opensciencegrid.org/docs/worker-node/install-singularity/#choosing-unprivileged-vs-privileged-singularity

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns.

OSG Security Team