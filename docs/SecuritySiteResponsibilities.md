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

### 4. Maintain up-to-date VO and user access information

### 5. Reporting and Responding to Security Incidents

### 6. Respond to requests from the OSG Security Officer 

### 7. Be familiar with the OSG Security web site

### 8. Maintain up-to-date Trusted CA/CRL information

