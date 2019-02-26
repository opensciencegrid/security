# OSG-SEC-2018-03-13 SAML Vulnerabilities affecting multiple implementations

Dear OSG Security Contacts,

This security advisory is INFORMATIONAL.

DuoLabs - the research team of Duo Security- has published the details of a new vulnerability that affects SAML-based single-sign-on (SSO) systems. "This vulnerability can allow an attacker with authenticated access to trick SAML systems into authenticating as a different user without knowledge of the victim user's password." [1]

## IMPACTED VERSIONS:
Multiple vendors and all SAML-based systems using these vulnerable libraries are affected by this flaw:

- OneLogin python-saml library before v2.4.0.
- OneLogin ruby-saml library before v1.7.2.
- Clever - saml2-js library from 1.12.3 to 1.12.4 and 2.0.1 to 2.0.2 
- Shibboleth  - XMLTooling library before V1.6.4. 
- Duo Network Gateway before version 1.2.10.

## WHAT IS THE VULNERABILITY:
The vulnerability is a flaw in some XML libraries and the way the text is extracted from the XML elements, particularly, when comments are included. In addition, XML canonicalization removes comments as part of signature validation; adding comments to a SAML Response will not invalidate the signature. Now, given that SAML Responses contain strings that identify the authenticating user, an attacker can impersonate a legitimate user and access protected information by modifying the SAML assertion and inserting a comment in the XML element that contains the Subject NameID [1].

The Common Vulnerabilities and Exposures (CVEs) numbers assigned for this vulnerability are listed below:

- OneLogin python-saml library: CVE-2017-11427
- OneLogin ruby-saml library: CVE-2017-11428
- Clever - saml2-js library: CVE-2017-11429
- Shibboleth - XMLTooling library: CVE-2018-0489
- Duo Network Gateway: CVE-2018-7340

## WHAT YOU SHOULD DO:
Apply updates and security patches for all the affected software to mitigate this vulnerability. Any systems that rely on SAML-based SSO should be patched ASAP:

- OneLogin - python-saml https://github.com/onelogin/python-saml/releases
- OneLogin - ruby-saml: https://github.com/onelogin/ruby-saml/releases
- Clever - saml2-js: https://engineering.clever.com/2018/02/28/clever-saml2-js-and-cve-2017-11429/
- Shibboleth XMLTooling library: https://shibboleth.net/community/advisories/secadv_20180227.txt
- Duo Network Gateway: https://duo.com/labs/psa/duo-psa-2017-003

## RELATED LINKS:
- https://ticket.grid.iu.edu/36412

## REFERENCES
- [1] https://duo.com/blog/duo-finds-saml-vulnerabilities-affecting-multiple-implementations

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team

