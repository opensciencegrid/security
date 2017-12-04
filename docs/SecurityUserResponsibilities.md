**What are Users' Responsibilities Regarding Security on OSG?**
===============================================================

About This Document
-------------------

As a user of OSG, you are responsible for three aspects of security:

-   Protecting your grid identity token
-   Abiding by the policies of your Virtual Organization (VO) that authorizes access to resources
-   Reporting known or suspected breaches of security

This document covers each of these areas of responsibility.

Protecting Your Grid Identity Token
-----------------------------------

The grid identity token is a PKI X509 digital certificate with a lifetime of one year, and a private key to which only the user has access. Protecting your grid identity means protecting your private key so that no one else is able to use (or misuse) it. Typically the private key is stored in a file called $HOME/.globus/userkey.pem. The (public) certificate needs to be accessible to parties and resources to which you'll need to authenticate yourself. It is typically stored in a file called $HOME/.globus/usercert.pem.

To protect your private key, please follow these security guidelines with respect to your `userkey.pem` file:

-   Copy `userkey.pem` to and/or store it only in a file that is accessible to yourself alone, i.e., to which no one else has privileges. In particular, observe the following:
    -   Do not keep unnecessary copies of it.
    -   Do not copy it to or store it in AFS or other shared file system.
    -   Do not copy it to or store it in a directory that is accessible to the network.
-   The private key must be encrypted with a suitably complex passphrase that only you know.
-   Typical Unix permissions should be 0400, readable only by owner.

You may also keep a copy of your certificate and private key in your web browser. Here, too, the private key must be encrypted using the features of your browser for encrypting keys and passwords. For Mozilla Firefox this is called the Master Password of the Software Security Device.

If your private key is compromised, please revoke your certificate immediately and get a new one (see [How do I get a user certificate in OSG?](https://opensciencegrid.github.io/docs/security/user-certs/)). If your VO does not provide instructions on revoking your certificate, then contact the registration authority (RA) that issued the certificate, or directly contact the certificate authority (CA) that issued it.

Abiding by the policies of your VO
----------------------------------

Every VO through which you access OSG resources has a science mission for which use of these resources is allowed. If you use OSG resources in a manner that is not directly or indirectly meeting the purpose of your VO, then you are in violation of the OSG acceptable use policy (AUP), and your VO can suspend your access to OSG resources.

Reporting known or suspected breaches of security
-------------------------------------------------

If you suspect or have knowledge of a security incident, please report it immediately to your local OSG grid security contact. For instructions, see: [Reporting a Security Incident](IncidentDiscoveryReporting).
