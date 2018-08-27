# OSG-SEC-2018-08-17 CPU speculative execution vulnerabilities (Foreshadow)

Dear OSG Security Contacts,

A new speculative execution-based attack similar to Meltdown and Spectre (CVE-2017-5754 [1]), has been reported in Intel processors. The L1 Terminal Fault (L1TF) also known as Foreshadow allows an attacker to gain access to sensitive data in the memory of any computing device. 

## IMPACTED VERSIONS/ENVIRONMENTS:

These vulnerabilities are present in the hardware and appear to affect all the operating systems running on x86 architectures. RedHat 6 & 7 and all its derivatives are impacted.

## ACTION RECOMMENDATIONS:

OSG Security team advises sites to patch all hosts, prioritizing CEs, submit hosts, and worker nodes ASAP. Patches for these vulnerabilities are expected to affect CPU performance. 

RedHat have mitigations available for kernel and microcode_ctl in RHEL6, RHEL7. Scientific Linux have mitigations available for kernel in SL6 and SL7.

RedHat Linux:
   - RHEL6: 
- kernel: https://access.redhat.com/errata/RHSA-2018:2390
- microcode_ctl: https://access.redhat.com/errata/RHEA-2018:2300
   - RHEL7: 
- kernel: https://access.redhat.com/errata/RHSA-2018:2384
- microcode_ctl: https://access.redhat.com/errata/RHEA-2018:2299

Scientific Linux:
   - SL6 (kernel): https://www.scientificlinux.org/category/sl-errata/slsa-20182390-1/
   - SL7 (kernel): https://www.scientificlinux.org/category/sl-errata/slsa-20182384-1/

There is a higher concern with virtualized environments. "..if two virtual machines share a physical core, then the virtual machine using one logical core can potentially spy on the virtual machine using the other logical core." [4] . For further mitigation, after installing the updated 
microcode_ctl patch, disable hyperthreading on virtual-machine hosts. An alternative is to change the configuration of the virtualized environment to ensure that virtual machines are bound to separate physical cores.

Note that existing mitigations and patches for Meltdown are *not* sufficient to protect against this new vulnerability. Some vendors have not released security patches for this vulnerability yet. Pay attention to new releases from your software vendor and patch as soon as the fix(es) become available. 

## HOW IT WORKS:
Privileged memory space can be accessed, exposing sensitive information. Details about the vulnerability and the attack can be found in [3].

## MORE INFORMATION:
* [1] http://www.theregister.co.uk/2018/01/04/intel_amd_arm_cpu_vulnerability/ 
* [2] https://www.intel.com/content/www/us/en/architecture-and-technology/l1tf.html
* [3] https://access.redhat.com/security/vulnerabilities/L1TF
* [4] https://arstechnica.com/gadgets/2018/08/intels-sgx-blown-wide-open-by-you-guessed-it-a-speculative-execution-attack/ 

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
