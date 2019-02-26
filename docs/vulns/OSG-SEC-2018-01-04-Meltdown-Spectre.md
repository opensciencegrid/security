# OSG-SEC-2018-01-04 CPU hardware vulnerabilities

Dear OSG Security Contacts,

Multiple hardware bugs have been reported in modern processors, particularly in Intel processors; these bugs or design flaws could enable access to sensitive data in the memory of any computing device. Chipmakers Intel, AMD and ARM have reported that their chips are affected at varying degrees by these bugs [1]. 

Two attacks, Meltdown [2] and Spectre [3] have been published and are being discussed extensively. The Meltdown exploit has been successfully tested on Intel processors and it is not clear yet whether ARM and AMD processors are also affected. The Spectre attack method can theoretically be performed on any CPU family; working exploits have been demonstrated on at least Intel, AMD, and ARM processor families.

These attacks have been particularly newsworthy as (a) the vulnerability is in a diverse cross-section of hardware, not software and (b) non-trivial performance impact of the mitigation techniques.  However, the severity is comparable to more mundane local privilege exploits against the kernel.

## IMPACTED VERSIONS:
These vulnerabilities are present in the hardware and appear to affect all operating systems, including Linux.  Available exploits can be performed by an unprivileged process or container against the host kernel and virtual machine against the hypervisor.

To exploit the vulnerabilities, an attacker needs the ability to execute arbitrary unprivileged code.  This privilege is commonly available to authorized users on OSG submit hosts, Computing Elements (CEs), or worker nodes.  No remote exploit is currently known.

## WHAT ARE THE VULNERABILITIES:
The vulnerabilities are design flaws in the way many modern microprocessor designs have implemented speculative execution of instructions (a commonly used performance optimization) [4]. 

The Spectre attack targets the vulnerabilities described in CVE-2017-5715 [5], CVE-2017-5753 [6] and the Meltdown attack, the one described in CVE-2017-5754 [7].

## WHAT YOU SHOULD DO:
These vulnerabilities are present in the hardware and cannot be entirely fixed by a software update of any operating system.  Mitigations exist that significantly limit the impact and increase the complexity of potential exploits.

The Meltdown vulnerability can be mitigated by available software patches; however, these patches incur a higher performance penalty than most security fixes.  RedHat has provided guidance [8] that HPC-style workflows should expect a 2-5% decrease in throughput; precise impact will depend on the host’s workload.

RedHat and Scientific Linux have mitigations available for kernel and microcode_ctl in RHEL6, RHEL7, SL6 and SL7. Additionally, there are updates for linux-firmware in RHEL7 and SL7. 

Please, **apply these security updates IMMEDIATELY**, especially on systems that are accessible by many unprivileged users. While some sites may find the performance decreases painful, OSG Security currently believes the benefits outweigh the costs.

OSG Security advises sites to patch all hosts, prioritizing CEs, submit hosts, and worker nodes.

RedHat Linux:
   - RHEL6
      - kernel: https://access.redhat.com/errata/RHSA-2018:0008
      - microcode_ctl: https://access.redhat.com/errata/RHSA-2018:0013
   - RHEL7
      - kernel: https://access.redhat.com/errata/RHSA-2018:0007
      - microcode_ctl: https://access.redhat.com/errata/RHSA-2018:0012
      - linux-firmware: https://access.redhat.com/errata/RHSA-2018:0014

Scientific Linux:
   - SL6
      - kernel: https://www.scientificlinux.org/category/sl-errata/slsa-20180008-1/
      - microcode_ctl: https://www.scientificlinux.org/category/sl-errata/slsa-20180013-1/
   - SL7
      - kernel: https://www.scientificlinux.org/category/sl-errata/slsa-20180007-1/
      - microcode_ctl: https://www.scientificlinux.org/category/sl-errata/slsa-20180012-1/
      - linux-firmware: https://www.scientificlinux.org/category/sl-errata/slsa-20180014-1/

## RELATED LINKS:
   - https://ticket.grid.iu.edu/35754

## REFERENCES:
- [1] http://www.theregister.co.uk/2018/01/04/intel_amd_arm_cpu_vulnerability/ 
- [2] https://meltdownattack.com/
- [3] https://spectreattack.com/
- [4] https://access.redhat.com/security/vulnerabilities/speculativeexecution
- [5] https://access.redhat.com/security/cve/CVE-2017-5715
- [6] https://access.redhat.com/security/cve/CVE-2017-5753
- [7] https://access.redhat.com/security/cve/CVE-2017-5754
- [8] https://access.redhat.com/articles/3307751

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
