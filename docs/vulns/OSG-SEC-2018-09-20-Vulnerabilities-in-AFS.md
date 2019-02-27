# OSG-SEC-2018-09-20 Vulnerabilities in AFS

Dear OSG Security Contacts, 

This announcement is for sites that use AFS. 

There are three new vulnerabilities described in CVE-2018-16947 [1], CVE-2018-16948 [2], and CVE-2018-16949 [3] which have been reported in AFS that could potentially allow an attacker to modify or delete data within the cells that have the backup tape controller (butc) process, could expose information to an attacker, and could cause a Denial of Service (DoS) attack respectively. OSG security team considers patching these vulnerabilities to be IMPORTANT.     

## IMPACTED VERSIONS/ENVIRONMENTS:
All releases of OpenAFS server/client prior to 1.6.23 are affected.
Also OpenAFS 1.8.0, 1.8.1, and 1.8.1.1 are affected. 

## ACTION RECOMMENDATIONS:
Upgrade to 1.8.2 or 1.6.23 releases. Please note that it is necessary to restart OpenAFS for the fixes to take effect. [4]

## HOW IT WORKS:
The backup tape controller process accepts incoming RPCs but does not require (or allow for) authentication of those RPCs. Handling those RPCs results in operations being performed with administrator credentials, including dumping/restoring volume contents and manipulating the backup database. [1] 

OpenAFS uses the Rx RPC protocol for all remote operations, and uses the rxgen utility to generate the server RPC stubs. Output variables are allocated either on the stack or on the heap, by the RPC handler (for variable-length arrays). Many RPC handlers did not fully initialize these output variables, leaking memory contents to the remote caller for otherwise-successful RPCs. [2] 

OpenAFS uses the Rx RPC protocol for all remote operations; RPC inputs and outputs are described using the XDR data description language. XDR includes a facility for variable-length (up to 4GB) arrays, optionally subject to a smaller bound on their size. For several RPCs, OpenAFS servers would accept and attempt to unmarshall into memory input arrays up to the full 4GB limit; length and authentication checks in RPC handler functions would be applied only after low-level memory allocation and unmarshalling. This allows unauthenticated attackers to consume large amounts of server memory and network bandwidth, producing service degradation or denial of service to legitimate clients. [3]

## MORE INFORMATION:
- [1] <http://www.openafs.org/pages/security/OPENAFS-SA-2018-001.txt>
- [2] <http://www.openafs.org/pages/security/OPENAFS-SA-2018-002.txt>
- [3] <http://www.openafs.org/pages/security/OPENAFS-SA-2018-003.txt>
- [4] <https://www.openafs.org/release/index.html>

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
