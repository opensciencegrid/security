# OSG Certificate Authority Distribution

## About This Document
The OSG Certificate Authority Distribution contains information about Certificate Authorities (CAs) in use in OSG.

## Contents
The OSG CA Distribution contains:

-   [IGTF Distribution of Authority Root Certificates](http://dist.eugridpma.info/distribution/igtf/current/) (CAs accredited by the [International Grid Trust Federation](http://igtf.net/))

For additional details, see the [distribution site](http://repo.opensciencegrid.org/pacman/cadist/) and [change log](http://repo.opensciencegrid.org/pacman/cadist/CHANGES).

[CA Certificate Installation and Update](https://opensciencegrid.org/docs/common/ca/) provides you with details of various options to install the Certificate Authority (CA) certificates and have up-to-date certificate revocation list (CRL) using OSG RPMs.

In the OSG repositories, there are two different sets of predefined CA certificates: osg-ca-certs and igtf-ca-certs. In the past, these two packages had different content and some unaccredited CA were distributed. As of February 19, 2018, the content of both packages is identical.

In order to enable authentication via CILogon for those who utilize it, as of August 8, 2018 a separate package is being offered which adds the CILogon OpenID Certification Authority Certificate to OSG 3.4. For additional details, see the [release notes for 3.4.16-2](http://opensciencegrid.org/docs/release/3.4/release-3-4-16-2/). This is a separate package that can be installed if desired.

## News
Effective 25 June 2010 the old FNAL_KCA has been removed, in OSG CA package version 1.15.

-   FNAL KCA (e1fce4e9)

*Production services on OSG should **NOT** install (or reference via yum or apt) the ITB version of the CA distribution since it may, at times, contain an untrustworthy CA certificate for testing purposes*

Effective March 10, 2009, the OSG Security Team has removed the following unused non-IGTF CAs from the OSG CA distribution:

-   PSC Kerberos CA (290a3b29)
-   PSC Root CA (9b88e95b)
-   PSC Hosts CA (acc06fda)
-   SDSC (3deda549)
-   NPACI (b89793e4)
-   TACC (9a1da9f9)
-   old NCSA CA (4a6cd8b1)

If you are aware of any use of these CAs in OSG, so that they should continue to be included in the OSG CA distribution, please notify <security@opensciencegrid.org> immediately.

## References
-   [OSG CA Certificates Hosted By GOC](http://repo.opensciencegrid.org/pacman/cadist/)
-   [OSG GOC Yum Repository](http://repo.opensciencegrid.org/)

