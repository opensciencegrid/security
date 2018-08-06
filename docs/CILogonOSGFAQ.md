# CILogon OSG CA

!!! warning 
    OSG CA stopped issuing certificates on May 31st, 2018. After this date, new certificates from the CILogon OSG CA cannot       be requested and therefore will no longer be issued.  All certificates issued by CILogon OSG CA will continue to work         until their expiration dates. The CILogon OSG CA will remain in the IGTF distribution until July 2019. 

Starting June 2016, the CILogon OSG CA is issuing certificates for users, hosts and services for OSG. The CILogon OSG CA is jointly operated with XSEDE. Combined with OSG Registration Authority and the OSG Information Management System, the CILogon OSG CA will provide the essential certificate services to the OSG community, including the personal, host and service certificates.

The transition from DigiCert CA to CILogon OSG CA was completed on May 31st, 2016. All user, host and service certificates are issued by CILogon OSG CA. All OSG Virtual Organizations (VOs) were transitioned successfully to CILogon OSG CA. All certificates issued by DigiCert CA will continue to work until its expiration date

## What are we using from CILogon?
Note, we are not using CILogon Basic CA. We are using CILogon HSM which is completely different from CILogon Basic. Note that CILogon has 4 different backend services and they are all different, we are using HSM. If you have a CILogon Basic certificate, you can continue to use that, but when you get a new certificate from OSG, you will get a CILogon HSM, not a CILogon Basic one, so it will be different.

- [How do I get user certificates?](https://opensciencegrid.org/docs/security/user-certs/)
- [How do I get host or server certificates?](https://opensciencegrid.org/docs/security/host-certs/)

## Frequently Asked Questions

### Does this transition mean that my local site will pay for certificates?
No. No changes to current process with regard to fees.

### What does this transition mean for the end user? What does the end user need to do to get new certificates?

Once end users' certificates are near expiring, they go to OIM to get a new certificate. The process is the same, but the distinguished name (DN) in the certifcate will be the new provider instead of DigiCert. Users will need to register their new DN with whatever services they access: DocDB?, twiki, etc. Note, the transition team will provide a script to automatically register the new DN with VOMS.

### I am a GridAdmin/RA Agent. Will I have the same privileges? If so, will you require anything from my home institution?
Yes, you will continue to act as a GridAdmin. Your home institution is not required to do anything for you to obtain this privilege.

### Will the new certificates be trusted by browsers so we don't get all sorts of warnings popping up?
Since the previous one was commercial, they paid money to be accepted by browsers. Warning messages may well pop up.
