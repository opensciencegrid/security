# OSG-SEC-2018-05-23 OSG CA service retirement

Dear OSG users,

This security advisory is INFORMATIONAL for the OSG community.

The OSG Security Team wants to inform you that as part of the OSG Service Migration [1], the CILogon OSG CA service will be retired on May 31st, 2018:
    -  After this date, new certificates from the CILogon OSG CA cannot be requested and therefore will no longer be issued.  
   - All certificates issued by CILogon OSG CA will continue to work until their expiration dates. 
   - The CILogon OSG CA will remain in the IGTF distribution until July 2019. 


## WHAT YOU SHOULD DO?

- Getting user certificates after the CILogon OSG CA retirement:
     - Non-LHC users can get certificates from the CILogon Basic CA (https://cilogon.org/) using their home institution credentials [1].
     - LHC users should continue to request their user certificates from CERN Grid CA (https://ca.cern.ch/ca/) [2].

- Getting host and service certificates after the CILogon OSG CA retirement:
    - Eligible institutions can get their host certificates from InCommon Federation certificate service [3].
    - Let’s Encrypt CA (https://letsencrypt.org/how-it-works/) also provides short-lived host certificates in a secure manner with a minimum of overhead and automated renewal [4]. Let's Encrypt CA has been added to the OSG CA certificates bundle [5].  

## REFERENCES:
- [1] https://opensciencegrid.org/technology/policy/service-migrations-spring-2018/
https://opensciencegrid.org/docs/security/user-certs/#getting-a-certificate-from-cilogon
- [2] https://ca.cern.ch/ca/Help/?kbid=021001
- [3] https://opensciencegrid.org/docs/security/host-certs/
- [4] https://opensciencegrid.org/docs/security/host-certs/
- [5] https://opensciencegrid.org/security/LetsEncryptOSGCAbundle/

## RELATED LINKS
 - https://ticket.grid.iu.edu/37926

Please contact the OSG security team at security@opensciencegrid.org immediately if you have any questions or concerns.

OSG Security Team

