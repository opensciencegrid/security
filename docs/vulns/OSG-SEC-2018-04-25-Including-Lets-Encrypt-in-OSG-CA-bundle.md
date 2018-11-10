# OSG-SEC-2018-04-25 Including Let’s Encrypt’s signing certificate in OSG CA bundle

Dear OSG Security Contacts,

This security advisory is INFORMATIONAL for OSG sites. 
 
As a part of the Service Migration Plan [1], we will be adding the Let’s Encrypt root certificate to the OSG CA certificate bundle. The OSG has traditionally included a handful of CAs in addition to the IGTF-Classic (https://www.igtf.net/ap/classic/) Certificate Authorities (CAs) for signing host certificates. These CAs often rely on manual, multi-step processes for signing certificates that add administrative overhead. Many modern operational environments would like to spin up hosts in response to changing user demand but the manual process often proves to be too slow for certificate procurement and revocation. Let’s Encrypt is an automated CA system that relies on a FQDN’s authoritative DNS records to identify and confirm a host’s identity.[3] Let’s Encrypt also provides short-lived certificates in a secure manner with a minimum of overhead and automated renewal.

Unlike the IGTF-Classic CAs, certificates from Let’s Encrypt will be recognized by your browser and OS by default.

Let’s Encrypt, however, does not confirm the organization that is running the host in the same manner as the IGTF-Classic CAs; we believe the additional IGTF checks are redundant with the registration and service discovery steps done on the OSG. OSG has separate registration procedures for services on the OSG that verifies the organizations; no access is given solely based on the possession of a host certificate. For more details please consult the OSG Information Security Officer’s position paper on the Let’s Encrypt CA for Host Certificate Signing. [2]

This is the upcoming change likely to be most relevant to security contacts during the migration. For more details on the migration plan please consult the Service Migration Plan document. [1] 

More Information:
- [1] https://opensciencegrid.github.io/technology/policy/service-migrations-spring-2018/ 
- [2] https://docs.google.com/document/d/17In575G9PawPzPGnPTSbqpDz2_9KVV3AlMgWNnHVKTQ/edit#
- [3] https://letsencrypt.org/how-it-works/ 

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

