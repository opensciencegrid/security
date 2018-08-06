# Incident Discovery and Reporting

## Reporting a problem
If you suspect a security problem, please **report it immediately**.

Also do NOT forget to report security incidents to your **local/home organization's** incident response team.

Please promptly report security incidents involving OSG resources via email to  <security@opensciencegrid.org>. 
Please include the following information in your report:

-   Your name, email address, phone number.
-   A description of the incident, including time(s), systems and user accounts involved, and any related event.
-   What is your affiliation with the OSG? Which Virtual Organization are you a member of?
-   Did this incident occur on a Site machine or on a VO machine or on your personal computer? Please provide detailed information (names, IPs, URLs, etc.) if you have
-   Do you think your grid identity (certificate and/or proxy) is compromised?
-   Any additional comments or questions you have

## What to do after an incident is reported

!!! note
    If you have not reported the incident to your local security team AND the OSG security team, report the incident now.

!!! note
    You will first want to notify your local security contacts. The local security contacts will help with hands-on examination. Then, make sure to report the incident to OSG.

### Compromised machine
If it is initially determined that the machine has been compromised, then here are a couple of steps to take:

!!! note
    Do not turn the machine off. There may be processes and/or live data that an incident responder may want to obtain on the machine.

!!! note
    Do not delete any files. Do not wipe off and re-install the system.

Get the machine off the network so it cannot do any more damage. The easiest way to do this will be to unplug the network cable from the machine. If this is a remote machine, or you are not sure where the machine is, then you will likely need to contact the local security or networking group and have them block the machine at the border or at the network jack. Take notes including timestamps of actions performed while investigating and isolating the machine.

### Compromised account
If you have determined that this incident has a compromised account(s) then you should follow below two steps:

#### Banning a user
#### Revoking a certificate
Whether you are an end user and have discovered that your certificate was compromised, or a system administrator who needs to revoke one or many certificates that were discovered to be compromised.

##### End user revoking a certificate
If you think that your certificate has been compromised in any way then it is the safest bet to go ahead and revoke your certificate and get a new one. Using the web browser where your certificate and private key are installed, go to the [OIM interface](http://oim.opensciencegrid.org/oim/certificate), choose the appropriate type of certificate and click on the Search button. Enter details as to why the certificate is being revoked and click on the Revoke button. You can get a new one afterward from the same location. There are currently no options to revoke a certificate from the command line. [Getting a new user certificate](https://opensciencegrid.github.io/docs/security/user-certs/).

##### System administrator revoking a certificate(s)
If you are a system administrator and have discovered that one (or more) user certificates on your system have been compromised then you will need to have these certificates revoked. Users can revoke their own certificates, but only a Registration Authority Agent (RAA) for a Certificate Authority (CA) can revoke a certificate not owned by them. So you will need to determine what CA's the certificates on your system belong to and then contact a RAA for that CA and have them revoke the certificates for you.

### Additional steps

If you are tasked with doing the forensic analysis, there are additional steps you can take. However, if an administrator or security engineer is going to be looking into the incident then you should leave the basic forensic analysis to them to insure that no data is destroyed during the investigation.
