# OSG-SEC-2021-05-11 Vulnerabilities in Squid

Dear OSG Security Contacts,

## SECOND UPDATE:

This is a followup to the announcement about vulnerabilities in Squid.  The OSG yum repository now contains the patched version frontier-squid-4.15-1.2.  All sites should upgrade.

The difference between version 4.15-1.1 and 4.15-1.2 is minor, and if you already upgraded to 4.15-1.1 from osg-testing you do not need to upgrade again.

## FIRST UPDATE:

This is a followup to the announcement earlier today about vulnerabilities in Squid.  We received feedback that the "WHAT YOU SHOULD DO" wording was ambiguous. We intended to recommend that everyone watch for and upgrade to frontier-squid-4.15-1.1 once it became available, but it could be read that that advice was only for Squids that had restricted destinations. The intended advice was only to limit the workaround to those with the highest risk and for everyone else to wait for the new version which was expected soon.

In the meanwhile, the new frontier-squid version has already become available in the osg-testing yum repository if you want to upgrade immediately. We will send another announcement when it becomes available in the OSG (production) repository.

## ORIGINAL ANNOUNCEMENT:

Multiple security vulnerabilities in Squid have been publicly announced [1].  The most important one allows bypassing access controls and the others enable Denial of Service attacks.

The OSG Security team considers the HTTP Request Smuggling vulnerability to be of HIGH severity.

## IMPACTED VERSIONS:

All frontier-squid versions prior to 4.15-1.1 are impacted. 

All Squid versions from Red Hat have the Denial of Service vulnerabilities, but the most important vulnerability was fixed in squid-3.5.20-17.el7_9.6 [2].

## WHAT ARE THE VULNERABILITIES:

The most important vulnerability is that due to improper input validation Squid is vulnerable to an HTTP Request Smuggling attack when there is whitespace in a URL. This enables anyone to bypass all access controls if they have access to read anything through the Squid. This especially impacts any Squids that restrict destination URLs, which is not the case for most site Squids, but it might also enable access to cache manager functions which are blocked by default.

The other vulnerabilities are potential Denial of Service vulnerabilities. The worst of those should already be blocked in most installations by their denial of the URN protocol.

## WHAT YOU SHOULD DO:

If you use frontier-squid and restrict the destination, as soon as possible update customize.sh with the following line and either reload or restart frontier-squid:

    setoption("uri_whitespace", "deny")

In addition, watch for a follow up announcement on the availability of frontier-squid-4.15-1.1 and upgrade to that version when it is available.

If you use the Red Hat EL7 Squid, update to squid-3.5.20-17.el7_9.6 and watch for further updates from Red Hat fixing the Denial of Service vulnerabilities. As of this time an update has not been made available for EL8.

## REFERENCES

[1] http://lists.squid-cache.org/pipermail/squid-announce/2021-May/000127.html

[2] https://access.redhat.com/security/cve/cve-2020-25097

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
