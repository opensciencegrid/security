# OSG-SEC-2018-02-28 Disable weak ciphers in SSL

Dear OSG Security Contacts,

This security announcement is informative and the intention is to remind OSG sites administrators to maintain secure configurations in their infrastructure at all times.  

In SSL and TLS, cipher suites define how secure communication takes place; and your TLS/SSL server always should select actively the best available cipher suite [1]. 

A recently published attack, named ROBOT [2], which targets TLS servers with weak ciphers enabled is just an example of another way that out-of-date cipher configuration can be abused. 

## WHAT YOU SHOULD DO:
- Disable weak ciphers in your OpenSSL configurations. We recommend consulting the Mozilla SSL Configuration Generator tool, which for example has good recommendations for Apache httpd on Redhat EL7 [3] and EL6 [4] and derivatives. The “Intermediate” level is sufficient for web servers as long as they don’t have access to any critical data; use “Modern” when you can.  The “Old” level is not acceptable. Although the Mozilla tool doesn’t offer “Modern” as an option for the EL6 Apache version, Redhat has added the support and the “Modern” parameters from EL7 work there (except for the SSLCompression option). 
- A good EL6/EL7 tool to check the ciphers accepted by https on a host is “sslscan <host> | grep Accepted”. 

## RELATED LINKS:
https://ticket.opensciencegrid.org/36295 

## REFERENCES

- [1] https://github.com/ssllabs/research/wiki/SSL-and-TLS-Deployment-Best-Practices
- [2] https://robotattack.org/
- [3] https://mozilla.github.io/server-side-tls/ssl-config-generator/?server=apache-2.4.6&openssl=1.0.2k&profile=modern
- [4] https://mozilla.github.io/server-side-tls/ssl-config-generator/?server=apache-2.2.15&openssl=1.0.1e

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team


