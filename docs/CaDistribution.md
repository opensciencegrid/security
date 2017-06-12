**OSG Certificate Authority Distribution**
==========================================

About This Document
-------------------

The OSG Certificate Authority Distribution contains information about Certificate Authorities (CAs) in use in OSG.

Contents
--------

The OSG CA Distribution contains:

-   [IGTF Distribution of Authority Root Certificates](http://dist.eugridpma.info/distribution/igtf/current/) (CAs accredited by the [International Grid Trust Federation](http://igtf.net/))
-   [Purdue TeraGrid CA](https://www.rcac.purdue.edu/services/xsede/)

For additional details, see the [distribution site](http://software.grid.iu.edu/pacman/cadist/) and [change log](http://software.grid.iu.edu/pacman/cadist/CHANGES).

[CA Certificate Installation and Update](https://twiki.grid.iu.edu/bin/view/Documentation/Release3/InstallCertAuth) provides you with details of various options to install the Certificate Authority (CA) certificates and have up-to-date certificate revocation list (CRL) using OSG RPMs.

News
----

Effective 25 June 2010 the old FNAL_KCA has been removed, in OSG CA package version 1.15.

-   FNAL KCA (e1fce4e9)

Beginning in May , 2010 OSG has started to provide a CA distribution for the integration test bed (ITB) separate from the production OSG distribution described below. Information about the ITB release is provided at <http://software-itb.grid.iu.edu/>.

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

See also:

-   [email announcement](http://listserv.fnal.gov/scripts/wa.exe?A2=ind0902&L=tg-security&T=0&P=67)

References
----------

-   [OSG CA Certificates Hosted By GOC](http://software.grid.iu.edu/pacman/cadist/)
-   [OSG GOC Yum Repository](http://yum.grid.iu.edu/)
-   [CA Certificates in the VDT](http://vdt.cs.wisc.edu/certificate_authorities.html)
-   [TeraGrid Approved CAs](https://www.xsede.org/home)

