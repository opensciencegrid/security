Dear OSG Security Contacts,

There are two new vulnerabilities in HTCondor described in CVE-2021-25312 [1] that allows a user to submit a job as another user on the system, because of a flaw in the IDTOKENS authentication method and CVE-2021-25311 [2] that allows directory traversal outside the SEC_CREDENTIAL_DIRECTORY_OAUTH directory, as demonstrated by creating a file under /etc that will later be executed by root. The HTCondor v8.9.11 release contains fixes for both the vulnerabilities.

The OSG Security team considers this vulnerability to be of HIGH severity.

IMPACTED VERSIONS:
HTCondor version 8.9.2 through 8.9.10. 


WHAT ARE THE VULNERABILITIES:
CVE-2021-25312: when a user is authenticating to a daemon using IDTOKENS it is possible for them to impersonate other users and/or the "condor" service itself. [3]

CVE-2021-25311: a running condor_credd daemon can be instructed to create or write certain files as root that are outside of the directory specified by the parameter "SEC_CREDENTIAL_DIRECTORY_OAUTH".

If you have not added the CREDD to your DAEMON_LIST, you are not vulnerable to this issue. (Keep in mind the CREDD is automatically added to the DAEMON_LIST if you have added "use feature:OAUTH"). [4]

WHAT YOU SHOULD DO:
Upgrade to version 8.9.11. 

RELATED LINKS

REFERENCES
[1] https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-25312 
[2] https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-25311 
[3] https://research.cs.wisc.edu/htcondor/security/vulnerabilities/HTCONDOR-2021-0001 
[4] https://research.cs.wisc.edu/htcondor/security/vulnerabilities/HTCONDOR-2021-0002 


Please contact the OSG security team [immediately] at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
