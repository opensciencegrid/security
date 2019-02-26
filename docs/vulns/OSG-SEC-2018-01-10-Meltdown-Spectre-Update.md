# OSG-SEC-2018-01-04 CPU hardware vulnerabilities 

## [UPDATE 2018-01-10]

Dear OSG Security Contacts,

This is an update of the security announcement about the CPU hardware in modern processors that were reported last week and are widely known as Meltdown and Spectre.  There is a new set of patches for those vulnerabilities that are applicable to Virtual Machine hypervisor hosts. 

## WHAT YOU SHOULD DO:
RedHat and Scientific Linux have published mitigations for the vulnerabilities in qemu-kvm and libvirt for RHEL6, RHEL7, SL6 and SL7.

Please, **apply these security updates IMMEDIATELY** on Virtual Machine hypervisor hosts, especially when the hosted Virtual Machines are accessible by many unprivileged users. While some sites may find the performance decreases painful, OSG Security team currently believes the benefits outweigh the costs.

OSG Security team advises sites to patch all hypervisor hosts, prioritizing those that host CEs, submit hosts, and worker nodes.

RedHat Linux:
   - RHEL6
      - qemu-kvm: https://access.redhat.com/errata/RHSA-2018:0024
      - libvirt: https://access.redhat.com/errata/RHSA-2018:0030
   - RHEL7
      - qemu-kvm: https://access.redhat.com/errata/RHSA-2018:0023
      - libvirt: https://access.redhat.com/errata/RHSA-2018:0029

Scientific Linux:
   - SL6
      - qemu-kvm: http://scientificlinux.org/category/sl-errata/slsa-20180024-1/
      - libvirt: http://scientificlinux.org/category/sl-errata/slsa-20180030-1/
   - SL7
      - qemu-kvm: http://scientificlinux.org/category/sl-errata/slsa-20180023-1/
      - libvirt: http://scientificlinux.org/category/sl-errata/slsa-20180029-1/


## RELATED LINKS:
   - https://ticket.grid.iu.edu/35754

## REFERENCES:
[1] https://access.redhat.com/articles/3307751

Please contact the OSG security team at security@opensciencegrid.org if you have any questions or concerns. 

OSG Security Team
