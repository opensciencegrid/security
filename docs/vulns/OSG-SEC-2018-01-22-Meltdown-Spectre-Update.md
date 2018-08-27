# OSG-SEC-2018-01-22 CPU hardware vulnerabilities [UPDATE]

Dear OSG Security Contacts,

This is an update of the security announcement about the CPU hardware in modern processors that were reported in the beginning of January and are widely known as Meltdown and Spectre.  Some instability issues were found in the firmware and microcode updates that caused some systems to not boot [1].  Redhat has reverted the updates with newer versions of the linux-firmware and microcode_ctl packages and instead recommends getting microcode updates directly from hardware vendors. 

## WHAT YOU SHOULD DO:
Apply the reverted patches as needed. Contact your hardware provider for the latest microcode/firmware updates. 

RedHat Linux:
- https://access.redhat.com/errata/RHSA-2018:0093
- https://access.redhat.com/errata/RHSA-2018:0094

Scientific Linux: 
- https://www.scientificlinux.org/category/sl-errata/slsa-20180093-1/
- https://www.scientificlinux.org/category/sl-errata/slsa-20180094-1/

## RELATED LINKS:
 - https://ticket.grid.iu.edu/35754

## REFERENCES:
[1] https://access.redhat.com/solutions/3315431

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team

