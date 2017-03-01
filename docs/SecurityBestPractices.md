**Security Best Practices**
===========================

About This Document
-------------------

This page documents security practices recommended by the OSG Security Team. Many of them may be discussed on other OSG web pages, but are also included here to try and maintain a thorough list as well as being able to cover more details on this page.

Risks for Grid Sites
--------------------

When sites become members of the OSG (or any other grid community) there may be additional risks to the local resources associated with grid computing. We try and outline some of these potential risks on the following page.

-   [Security Risks of Grid Resources](https://twiki.grid.iu.edu/bin/view/Documentation/SecurityRisksCE)

Communicate with Security Team
------------------------------

-   **Notify security team of any incidents**.
    -   This is the primary requirement the OSG security team places on the site admin.
    -   Procedures to report security incidents are identified [here](IncidentDiscoveryReporting)
-   We ask users and sites to report incidents so that we can
    -   Access the risk it poses to the OSG at large
    -   Notice any patterns in the attacks
    -   Notify sites with attack information
    -   Contain the spread of the incident/attack
-   Communication during incident is critical
    -   Emails from/to the security team should be signed
    -   Take actions advised by security team promptly
    -   Need to send encrypted data. Instructions [here](SecureEmail)
-   We work with you to keep your security incident information you send us confidential
    -   We release to OSG site/VO security contacts only as much information as necessary to maintain security
-   Know your local institutions cyber-security contacts and report incidents to then in addition to OSG security team.
-   When you have questions **ASK**
    -   Questions could be on general UNIX security in general or specific Grid security topics.
    -   You may have questions about specific OSG polices and procedures.
    -   OSG security team and/or your fellow OSG site administrators will more often than not be able to help address your questions.
    -   **PLEASE, JUST ASK**. <osg-security-team@opensciencegrid.org>.

System Updates
--------------

Promptly apply security updates from software vendors, including operating system kernel updates and VDT updates. This has been mentioned multiple times on our other OSG security pages, but it is still one of the best ways to protect your systems from compromise.

Resources:

-   Update between minor OSG revisions
    -   Updating between minor OSG releases has been drastically improved
    -   Please promptly install the latest OSG update.
-   [VDT Update Information](http://vdt.cs.wisc.edu/documentation.html)
-   [Red Hat Network](https://www.redhat.com/rhn/): Automates updates for Red Hat Linux systems.

Securing Services on Grid Machines
----------------------------------

All of your grid nodes should be configured with the best practice guideline of not running any services on the machine which are not needed. So if local SSH access is not needed on your CE's then do not enable GSI-SSH. Another good stance to take is don't implicitly trust your local users. So patching against local vulnerabilities can be just as important as patching against remote vulnerabilities. You cannot protect against a remote users desktop getting compromised and then being used as an attack against your systems. Lastly, even if users do not have interactive login access to your machines they can still run pretty much anything they want with submitting jobs. So keep your machines patched and running with the minimal services needed.

Security for Application Administrators
---------------------------------------

VO Application Administrators are expected to:

-   (**at a bare minimum**) Ensure that their software does not compromise the security of any site upon which it runs;
-   Ensure that the software installation procedures follow all posted OSG security policies and procedures (see the [OSG security pages](index) for more details);
-   Ensure that the software installation procedures follow all posted site-specific security policies and procedures for those sites where the software is installed and run (see each site's entry on [MyOSG](http://myosg.grid.iu.edu/));
-   Ensure that their software and the installation and execution thereof is consistent with the VO's own posted policies, procedures and purpose (which should be posted and up to date on [MyOSG](http://myosg.grid.iu.edu/));
-   Promptly follow the [incident reporting procedures](IncidentDiscoveryReporting) in the event that a security problem is discovered.

Incident Handling
-----------------

Promptly report security incidents involving OSG resources according to [these instructions](IncidentDiscoveryReporting).

Resources:

-   [Banning User DNs at your site](https://twiki.grid.iu.edu/bin/view/Documentation/Release3/BanningUsersAtSite)
-   [Basic Forensics Techniques](https://twiki.grid.iu.edu/bin/view/Documentation/BasicForensics)

Monitoring
----------

Monitor for suspicious activity such as

-   connection attempts from suspicious IP addresses
-   instances of suspicious ssh keys, files, and malware

Recommended monitoring tools:

-   [Logwatch](http://www.logwatch.org/): A customizable log analysis system.
-   [Samhain](http://www.la-samhna.de/samhain/): A host-based intrusion detection system (HIDS).
-   [Bro](http://www.bro-ids.org/): A network intrusion detection system (NIDS).
-   [chkrootkit](http://www.chkrootkit.org/): A tool to locally check for signs of a rootkit.

Firewalls and Blocking Hosts
----------------------------

Use firewalls to restrict access to system services:

-   Allow ssh connections (port 22) only from trusted hosts. See [SshHostsAllow](https://twiki.grid.iu.edu/bin/view/Documentation/SshHostsAllow) for documentation on how to restrict access using `/etc/hosts.allow` and `/etc/hosts.deny`.

Firewall resources:

-   [VDT and Firewalls](http://vdt.cs.wisc.edu/releases/1.10.1/firewall.html) - lists all ports used with VDT software.
-   [iptables](http://www.netfilter.org/projects/iptables/): The command-line program for configuring the Linux firewall.

Another option for blocking hosts is using the [DenyHosts package](http://denyhosts.sourceforge.net/features.html). This package can help protect against the constant SSH brute force attacks. It will watch the system logs and detect when a brute force attack is occurring and then block the offending host in real time. There are many other nice features that [DenyHosts](http://denyhosts.sourceforge.net/features.html) also provides.

Mapping Grid DN's to Local Accounts
-----------------------------------

At some point sites are going to need to decide on how to map users grid DN's to local accounts. Traditionally OSG has not mandated to sites how they need to map accounts, this has been delegated to the VO's. There are a couple models that VO's have used, and we'll touch on the security implications for each of these methods.

### Mapping DN's to a local VO account (group account)

This is one of the easiest ways to enable users within VO's to run jobs at your site. You only need to create one local user for each VO you are going to allow access, then each of the individual user's DN's within that VO will map to that local account. Though this may be the easiest to configure, it may be one of the less secure methods. Since all users are mapped to the same local account, that account is acting like a group account. When a problem may occur it could lead to difficulty in tracking down which user in the VO may have caused the problem. Also, since it is a group account all users will have access to any source or data files that are in that local accounts directory. Some users may clean up after themselves when a job is finished, but others may not. There may be VO's with a small number of users, who happen to share all their data and code, where this method would work great. Still, many of the VO's do choose to use this method. The risk of this method is primarily risk to the VO, and not the local site since all the the VO's users will be sharing the same account.

### Mapping DN's to a static pool of accounts

With this method a pool of accounts is created for each VO where the number of accounts will be equal to the number of users in each VO. Then each unique DN is mapped to a unique account within the VO pool. This is the most secure method of mapping DN's to local accounts. In this case no user should ever be able to see another users source or data files, as well as having a straightforward auditing capability to track problems with a local account to the specific user. There are some additional administration items to cover in this method (such as needing to create potentially hundreds or thousands of local accounts for a VO), but the benefits of this usually outweigh the overhead.

### Mapping all DN's (in all VO's) to one account

This method is NOT a supported configuration within OSG. If it is discovered that a site has mapped all DN's in all VO's to one account then we will work with them on modifying their configuration to one of the above valid options. The security implications of this is hopefully obvious to most admins where any data, source code, etc. will be accessible to all users in any VO.

SSH Keys
--------

Protect SSH private keys with passphrases. There have been recent attacks at grid sites where miscreants are stealing users ssh keys, searching for keys without pass phrases, and then using those to attack other sites.

Also don't share keys. Your account is your own (and you are responsible for it).

Simple ways to monitor your systems for SSH activity (Look at Monitoring Ssh Activity)

Account Passwords
-----------------

There has been a ton of research into the use and security of passwords. But a few of the most basic security practices for passwords are:

Use different passwords for different accounts. Sharing passwords across different accounts may seem to make it easier, but it can also be more damaging if one of the many accounts gets compromised.

Always use good passwords. It is good practice to use different character classes in passwords (upper, lower, numerical, special characters, etc.). Also, pass phrases are becoming very popular to user rather than passwords. So instead of using an 8 character password, you can use a much longer pass phrase (which may even be easier to remember), such as something like "B3tter0ffDead" (3 different character classes and 13 characters long). But don't use that one...

Security Considerations when using GUMS
---------------------------------------

There is a section in the [GUMS online documentation](https://www.racf.bnl.gov/Facility/GUMS/1.4/) that addresses the [security considerations to take when running a GUMS server](https://www.racf.bnl.gov/Facility/GUMS/1.4/installation_security.html).

Hands-on Training
-----------------

-    [Security Training](https://twiki.grid.iu.edu/bin/edit/Security/SecurityHandsOnTraining?topicparent=Documentation.SecurityBestPractices) (from OSG All Hands Meeting, Baron Rouge, LA, Mar 2, 2009)

Reference Materials
-------------------

-   [A How-To Guide for Basic Linux Security](http://tldp.org/HOWTO/Security-HOWTO/)
-   [O Reilly - Practical UNIX & Internet Security](http://oreilly.com/catalog/9780596003234/)

