# OSG-SEC-2020-02-07 Vulnerabilities in Frontier-Squid

Dear OSG Security Contacts,

Security vulnerabilities have been publicly announced for squid.  OSG has released a version of frontier-squid with fixes for the vulnerabilities.  All installations of squid should be upgraded.  OSG security considers the vulnerability affecting reverse proxy installations (such as CVMFS Stratum 1 servers) to be CRITICAL and the vulnerability affecting ordinary proxy installations to be MODERATE.

## IMPACTED VERSIONS:

All versions of frontier-squid prior to 4.10-1.1

## WHAT ARE THE VULNERABILITIES:

The first vulnerability [1] affects reverse proxy configurations, where squid forwards all traffic to a backend server using the http_port "accel" or "vhost" options.  CVMFS Stratum 1 servers are affected.  Due to incorrect input validation, squid can interpret crafted HTTP requests in unexpected ways to access server resources prohibited by earlier security filters. Also, due to incorrect buffer management a remote client can cause a buffer overflow in a Squid acting as reverse-proxy.  This can result in remote code execution.

The second vulnerability [2] affects squid installations that allow proxying ftp, which is the default. Due to incorrect data management, squid is vulnerable to information disclosure when translating FTP server listings into HTTP responses.  The information may be anything from the heap area including information from other processes on the machine.  An exploit requires control of the destination server, so those installations that restrict the destination servers to a known list of trusted servers should not be affected, but OSG security still advises upgrading.

## WHAT YOU SHOULD DO:

AUpgrade reverse proxy installations to frontier-squid-4.10-1.1 as soon as possible, and schedule an upgrade for other installations.

## REFERENCES

[1] http://www.squid-cache.org/Advisories/SQUID-2020_1.txt

[2] http://www.squid-cache.org/Advisories/SQUID-2020_2.txt

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns.

OSG Security Team