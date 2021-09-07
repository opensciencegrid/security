# OSG-SEC-2021-07-27 Vulnerabilities in HTCondor

Dear OSG Security Contacts,

Two security vulnerabilities have been discovered in HTCondor, HTCONDOR-2021-0003 [1] and HTCONDOR-2021-0004 [2], both of which allow unprivileged users to perform unauthorized actions.

The OSG Security team considers these vulnerabilities to be of HIGH severity and recommend updating HTCondor to the fixed version as soon as possible.

## IMPACTED VERSIONS:

HTCONDOR-2021-0003 affects SchedD and Collector components in all versions of HTCondor.
HTCONDOR-2021-0004 affects all daemons from version 9.0.0 and above.

## WHAT IS THE VULNERABILITY:

HTCONDOR-2021-003 allows a user with read access to a SchedD or Collector to discover secrets that could allow them to control other user's jobs and/or read their data.

HTCONDOR-2021-004 may allow users bearing a SciToken to be granted authorizations beyond what the token should allow.

## WHAT YOU SHOULD DO:

Update any HTCondor-CEs, HTCondor access points, and HTCondor central managers to a fixed version of the software [3] (8.8.14, 9.0.3 or 9.1.1) as soon as reasonably possible.

A workaround for HTCONDOR-2021-0004 can be implemented by not allowing SciTokens as an authentication method until the patch can be applied. This means overriding the list of authentication methods (which includes SciTokens by default) by setting SEC_DEFAULT_AUTHENTICATION_METHODS to all the methods you would actually like to use. To simply remove SciTokens, set it to "FS,TOKEN,KERBEROS,GSI,SSL". [2]

## REFERENCES

[1] https://research.cs.wisc.edu/htcondor/security/vulnerabilities/HTCONDOR-2021-0003-8b300a1e.html

[2] https://research.cs.wisc.edu/htcondor/security/vulnerabilities/HTCONDOR-2021-0004-e92cd87d.html

[3] https://research.cs.wisc.edu/htcondor/downloads.html

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns.

OSG Security Team
