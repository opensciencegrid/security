# OSG-SEC-2020-08-31 Vulnerabilities in frontier-squid

Dear OSG Security Contacts,

The squid project has publicly announced new vulnerabilities that can result in cache poisoning.  OSG has released a new version frontier-squid-4.13-1.1 that addresses the vulnerabilities, and all sites are encouraged to upgrade to it.  There is also a temporary workaround that may work for sites that cannot upgrade in a timely manner.

## IMPACTED VERSIONS:

All frontier-squid versions < 4.13

## WHAT ARE THE VULNERABILITIES:

Two announced vulnerabilities, one for request splitting [1] and one for request smuggling [2] can both lead to cache poisoning.  Cache poisoning will lead to only denial of service for CVMFS, but could potentially be more serious for the Frontier application used by CMS and ATLAS, or for other applications that might be using the squid.  Note that exposure to squids is usually limited by access control to addresses within a local area network.

## WHAT YOU SHOULD DO:

On RHEL6 or RHEL7, upgrade squid with 
	
  ```yum install frontier-squid```
  
as shown in the OSG frontier-squid installation instructions [3].  The squid will be out of service for about a minute during the upgrade.  The new version is available in OSG 3.4 and 3.5 yum repositories.

An alternative workaround for the vulnerabilities is to add the option 
	
  ```setoption("relaxed_header_parser", "off")```
  
to /etc/squid/customize.sh and reload the squid with
	```service frontier-squid reload```
This has been tested with CVMFS and Frontier but may impact other applications using the squid.

## REFERENCES

[1] https://github.com/squid-cache/squid/security/advisories/GHSA-c7p8-xqhm-49wv

[2] https://github.com/squid-cache/squid/security/advisories/GHSA-3365-q9qx-f98m

[3] https://opensciencegrid.org/docs/data/frontier-squid

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
