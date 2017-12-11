# Site Responsibilities for Security

## About This Document

This describes the expectations and actions that a site administrator handles regarding security issues as a participant in OSG.

## First, our (OSG security team) responsibilities for sites

Our goal is to minimize disruptions caused by attacks or security problems so that your work is more effective and the computational resources are more productive. We recognize that participating in and operating grid resources and infrastructure is a learning experience for all of us. In addition to keeping up with vulnerabilities discovered with the grid middleware and having a security process intended to reduce the likelihood that security problems cause a significant disruption to the productive use of the resources, we strive to provide helpful information and assistance to site administrators (and other grid participants). We are sure that the information provided to site administrators and grid users is incomplete and could be greatly improved. We hope (and would like) that site administrators (and others) that have questions will ask. And, one of the main reasons that documentation is maintained on the TWIKI is so that everyone can be a participant in improving the information.

### We are happy to answer questions

Recognizing the inherent limitations in the documented information about OSG, and because we enjoy getting to know the other people in our grid community, we expect to get questions, and are happy to answer them (if we know the answer). And if we don't know the answer we probably have an idea about where to find the answer. But we can't answer questions unless you ask, so please ask. Remember, there are no stupid questions, only stupid answers.

If your question is about a suspicious behavior, possibly an incident, then email us at <security@opensciencegrid.org>. This is a 24\*7 alert list that we immediately respond to.

### How can we help you more effectively?

Don't hesitate to tell us how we can be more effective or to ask a question. You can email <security@opensciencegrid.org> or contact one of the security [team members](https://opensciencegrid.github.io/security/#team-members) individually.

## Background

It is expected that the administrative and security contacts for a resource registered with OSG (in OIM) are capable of dealing with the normal system administration and security practices of running a cluster of machines for scientific computing. The security materials provided on the OSG twiki occasionally mention examples of how basic computer security features could be handled but that is not a replacement for formal in-depth training on unix system administration.

Having said that we know that some small site admins (e.g. Tier-3s) may not have much experience in system level security. We have started collecting some examples in a Documentation.SecurityBestPractices page (which you are welcome to contribute to). If there are particular issues that you would like to learn more about (e.g. firewall configuration, linux updates), we can gladly point you to more specific resources. We may not have the effort to train you on basic security topics, but we will try our best to give you resources and put you in the right direction. Let us know!

## Site Security Responsibilities

The following are the top security items that sites need to follow as members in the OSG. 

### 1. Security contact information in OIM

Site security contacts can update their contact information from the OSG Information Management (OIM) system by clicking the Profile link at the top. However, you will need a personal X.509 certificate in your web browser in order to register with OIM and for access to update your information. The OSG will do a periodic assessment of the contact information (once a year) to remind users to keep their information up-to-date. But it is expected that people will keep their own information current.

!!! note
    Even if there are no changes to your contact information on your profile page you will still need to update your confirmation date. At the bottom of your profile page there is a "Confirmation" section. You will need to click on the "Update Confirmation Date", and then you MUST also click on the "Submit" button at the bottom in order for the new confirmation date to take affect.

!!! note
    Please update OIM and notify the GOC whenever the operations or security contacts for your site changes.

!!! note
    Maintaining valid contact information is 50% of being a GREAT site admin! Seriously. We will send you security patch notices, updates, instructions for risk mitigation, and so on. Without valid contact information your site will not get these important notices. Also, if you become unresponsive to all of our notification attempts, we will start thinking your site is no longer participating in the OSG.
    
### 2. Read Security Notifications from OSG

OSG sends out security notifications to all security contacts when important events occur, such as a vulnerability notice requiring a software update. If you receive a notice you are expected to read it and the detailed information linked to a GOC ticket (if there is a link).

!!! note
    You will need your personal certificate that is registered with OIM in your browser in order to read the details of the notice in the ticket.
    
### 3. Know your institutional cyber security officer

Most institutions have someone responsible for cyber security at the institution, usually reporting to the CIO (Chief Information Officer) of the institution. The person responsible may have the title of Cyber Security Officer, or Computer Protection Program Manager, or some other title. They are typically responsible for security of the central IT systems, network security, and security awareness training for the users at that institution. You should know who that person is. If you don't know who that is, consider the following scenario:

*A suspicious process is found running on one of your compute elements. Doing some initial checks it appears that there may be some additional problems on the machine and a rootkit may be installed. Who is going to come help investigate? It will likely be someone from the local cyber security officer's team. They will also likely have the resources and data to determine the extent of the compromise at your site and the risks to the other machines on the network.*

*You should introduce yourself to the cyber security officer and discuss any institutional requirements for the operation of your grid site. Remember your local security team is always the primary party responsible for the security of your site. They may want to understand what your participation in OSG means.*

### 4. Maintain up-to-date VO and user access information

Each VO on OSG keeps a up-to-date list of their members. These are the users that should be given access to sites on behalf of the VOs. It is important to keep these lists up to date so that when VO removes a user for whatever reason, your site would also stop providing access to the particular user.

### 5. Reporting and Responding to Security Incidents

The goal of the OSG security team in incident handling is to first contain the incident to prevent it from spreading, and then to help the site administrators diagnose the cause or vulnerability of the incident. Then we can learn from the incident and improve the infrastructure accordingly. Because we are participating in a world wide infrastructure, the OSG will confidentially share information about incidents that is relevant to our partners in other countries. This means that we will keep you in the loop before we disclose any information about your site. When you first contact us, we will work with you and your local security team to decide what information we can share with other communities. We will not endanger your site's public reputation. We will share information when we believe other grid sites also subject to the same attack.
Any circumstance that causes the grid credentials (X.509 certificate private key or proxy certificate) to be compromised should be reported to the OSG. What does compromised mean? It means the private key of an X.509 certificate, or a proxy certificate file, is accessible to someone or some process which is not the owner of the credential (not counting the root account). Also, if the root account is hacked on any system which stores X.509 private keys or proxy certificate files then all those credentials should be considered compromised. If you have evidence that the compromised credentials were actually used by the intruder, that should be reported as well. Note that these credentials can be either for a person or for a host or service. If it is an X.509 certificate private key that is compromised, that should also be reported to the issuing Certificate Authority so that certificate can be revoked.

If any system which runs grid services, hosts grid software, or runs grid batch jobs has its root account hacked, then that incident should be reported to OSG.

When an incident is confidentially reported to the OSG then someone from the OSG security team will follow-up with the site and proceed according to the circumstances.

### 6. Respond to requests from the OSG Security Officer 

In many ways, the most important security requirement for running a site is that you communicate with the OSG Security Officer and the Security Team. When issues come up or incidents occur there is usually some manual intervention required and this means reading email from the OSG security team or taking phone calls (in the most urgent cases). In order to be sure that OSG can communicate with the site administrator responsible for security of a site there is the periodic update of contact information in OIM.
If you have confidential information to provide to the OSG security team, it can be sent via encrypted email or submitted as a security ticket to the GOC (requires a registered X509 certificate in your browser). Of course, you can always use the telephone as well for secure communications (call the GOC or individual security team members).

!!! note
    Anything you tell OSG security team in confidentiality will be kept confidential. We will not share it with any other parties, including other sites, VOs, and OSG management. Of course, if the preservation of the information presents an imminent threat against the security of OSG, we may need to share it with other parties. BUT, before doing that we will inform you first, and decide how much to disclose and how to disclose the information.

### 7. Be familiar with the OSG Security web site

Information regarding incident handling, security best practices, awareness training, procedures, etc. is linked from the main OSG Security twiki page. You should familiarize yourself with this information and browse through it before you have a security incident. Especially the sections marked URGENT and Security Awareness for OSG Participants. If you have any questions about any of the material ASK.

### 8. Communicate Securely

The OSG Security team encourages the use of secure email communication. All official announcements from the OSG security team will be digitally signed. We encourage you to verify the digital signatures on OSG security announcements. Also when sending sensitive information to the OSG security team, we encourage you to encrypt your messages. More information [here](SecureCommunicationsOSG)

### 8. [Maintain up-to-date Trusted CA/CRL information](https://opensciencegrid.github.io/docs/common/ca/)

