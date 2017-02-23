Frequently Asked Questions about the Open Science Grid
======================================================


General Information
-------------------

**What is the Open Science Grid (OSG)?**

  The Open Science Grid brings together a distributed, peta-scale computing and storage resources into a uniform shared cyberinfrastructure for large-scale scientific research. It is built and operated by a consortium of universities, national laboratories, scientific collaborations and software developers. [Read more...](Documentation.WhatIsOSG)

**Who funds the OSG?**

  The OSG is supported by the National Science Foundation and the U.S. Department of Energy's Office of Science. Funding for work done at sites and by partners comes from a variety of sources specific to that site or organization.    

**Does OSG control the OSG resources?**

  No, individual resource owners do.

**What services are available in the OSG?**
  
  Job submission, data transfer and storage, authentication, accounting, monitoring, central information gathering/publishing, web caching (proxy), and more. [Read more...](OverviewOfServicesInOSG)   

**What is the GLUE schema used in OSG?**
  
  The GLUE Schema is an abstract model for Grid resources that can be used in Grid Information Services. [Read more...](http://forge.gridforum.org/sf/projects/glue-wg)    

**Who participates in the OSG?**
  
  The Open Science Grid is a collaboration of science researchers, software developers and computing, storage and network providers who come from universities, national laboratories and computing centers. Although based primarily in the United States, the OSG includes participants in other nations. [Read more...](Management.OSGMemberOrganizations)

   
Getting Started
---------------

**Where can I get funding to convert my applications to parallelism needed on the OSG?**
  
  The OSG can provide assistance with [installation and administration of OSG sites](Documentation.Release3.WebHome), installation and use of [client software](Documentation.Release3.InstallOSGClient) to run grid jobs on the OSG, and [User Help](Documentation.UserHelp) in enabling your application for the grid. But the OSG does not provide funding for this process.   

**What application requirements are *NOT* well-suited to the OSG?** 
  
  Applications that require:
  
    * Input from the user during execution. However, applications of this kind can often be rewritten so as to not require the interaction, or to decrease it to levels where the grid's resources can provide substantial runtime improvements.
    * A large ammount of inter-process communication between jobs (for example, needing MPI); very few sites are currently MPI-enabled.
    * Strict schedules and dependencies on external data sources.
    * Excessive bandwidth between sites.
    * Firm and nonstandard system dependencies.
    * Inter-process communication on the grid servers, including complex job flows network ports or protocols that are not disallowed at the grid site. For the most part it is preferable to pre-stage the data at the site rather than pull in large datasets. 
    
(Adapted from Ferreira, et al (2004), [Grid Services Programming and Application Enablement(http://www.redbooks.ibm.com/abstracts/sg246100.html?Open)  pp. 76.)

**How do I use the OSG resources?**
  
  To get started using the OSG infrastructure, you must:
    1. Join a [Virtual Organization](https://twiki.grid.iu.edu/bin/view/Documentation/GlossaryOfTerms#DefsVo) registered with OSG
    2. Download and install the OSG client software, or the customized version for your Virtual Organization
    3. Enable your appllication for grid computing
    4. Submit your job to a resource available to your Virtual Organization

[Read more...](Documentation.Release3.NavUserMain)   

**Where can I get training on how to use the grid?**
  
  The [Education, Training and Outreach activity](Education.WebHome) offers grid schools and workshops in a variety of locations across the US and abroad. Your group can sponsor a grid school at your facility. The grid school tutorial labs are available online and can be done by individuals on their own, requiring only access to an OSG compute element.   

**How do I port my existing application to work on the OSG resources?**
  
  See links under in [User Resources](Documentation.Release3.NavUserResources) and [Porting Your Application](PortingYourApplication). 

**Is there a glossary of grid computing terms?**
  
  Yes, see the [glossary of OSG terms](GlossaryOfTerms).   

**How do I get permission to edit information on the Page?**

  1. [Fork the repository from GitHub](https://github.com/opensciencegrid/secuirty)
  2. Submit a pull request to the repository after making changes


Virtual Organizations (VO)
--------------------------

**What is an OSG Virtual Organization (VO)?**
 A Virtual Organization (VO) is collection of persons. Members of a VO may come from many different home institutions in geographically separate places, may have in common only a general interest or goal (e.g., CMS physics analysis), and may communicate and coordinate their work solely through information technology (hence the term virtual). [Read more...](https://twiki.grid.iu.edu/bin/view/Documentation/GlossaryOfTerms#DefsVo)    

**Do I have to be part of a VO in order to use or contribute to OSG?**
  
  Yes. Learn more about VOs from [the Virtual Organizations page](Documentation.WhatIsVO).   

**Where do I find which VOs are already registered with OSG?**
  
  See the [current VO list](https://oim.grid.iu.edu/oim/vo).   

**If I'm not part of a registered VO and my research group can't support a VO, what are my options?**
  
  You may join the VO named (confusingly) "OSG".

**How do I join an OSG Virtual Organization (VO)?** 
  
  Different VOs may have different membership requirements and procedures. You will first need to determine which VO is most appropriate for you to join, then either see that VOs web pages or go to the [VO List](https://oim.grid.iu.edu/oim/vo) for links to that VO's membership procedures. [Read more...](Documentation.WhatIsVO)   

**So many acronyms start with "VO"; how do I keep them straight?**
  
  Read [VO](https://twiki.grid.iu.edu/bin/view/Documentation/GlossaryOfTerms#DefsVo).   

**How does a VO fit into the OSG?**
  
  Read [How does a VO fit into the OSG?](VOAdminInOsg).    

**How do I form a new VO?**
  
  [Contact User Support](UserHelp) if you want to form a new VO.   

   
Getting Support
---------------

**How do I get support for problems I encounter while using OSG resources?**
  
  Users typically get support through contacting your [VO's support center](http://myosg.grid.iu.edu/scsummary?datasource=summary&summary_attrs_showdesc=on&all_scs=on&active=on&active_value=1). Site administrators often use the *osg-general* and *osg-int* mailing lists. [Read more about getting user help and support...](UserHelp)    

**What is the Grid Operations Center (GOC)?** 
  
  See [What is the Grid Operations Center (GOC)?](GocWhatIs) or go directly to [Grid Operations Center](http://osggoc.blogspot.com/).   

**What OSG mailing lists should I subscribe to?**
  
  The OSG's mailing lists are categorized and described on the [mailing lists](ContactsMailingLists) page. Some are used to distribute announcements, others to provide discussion forums, activity coordination forums, and so on. We suggest that everyone subscribe to *OSG*, *OSGNEWS*, and *OSG-GENERAL* (all *@opensciencegrid.org*). Further subscriptions should be based on the types of activities you become involved in.   

   
Running Jobs
------------

**How do I run a job on an OSG resource?** 
  
  This is often specific to your particular VO's policies and procedures. However we provide some links under the heading "End Users (Researchers, application users)" on the [Documentation hub](WebHome) with some OSG-generic information.    

**How can I monitor my OSG work?** 
  
  There are multiple monitoring infrastuctures to provide targeted views of the distributed facility. You can receive periodic reports by subscribing to the *osg-ops-status* email list (*@opensciencegrid.org*). Read more information in [OSG Grid Monitoring](Trash/MonitoringInformation.WebHome).    

**How do I troubleshoot a job that is not running properly?**
  
  OSG has a [Troubleshooting Guide](Documentation.Release3.TroubleshootingGuide) or you can contact [User Help](Documentation.UserHelp).    

**Can I really run my job on any OSG resource without talking to the site first?**
  
  Almost. You can run your job on any OSG site that allows users from your Virtual Organization. Many sites allow users from all OSG VOs. The VOs allowed to run on each resource can be found in the [OSG Resource List](https://myosg.grid.iu.edu/rgsummary/index?datasource=summary&summary_attrs_showservice=on&summary_attrs_showrsvstatus=on&summary_attrs_showfqdn=on&summary_attrs_showvomembership=on&gip_status_attrs_showtestresults=on&downtime_attrs_showpast=&account_type=cumulative_hours&ce_account_type=gip_vo&se_account_type=vo_transfer_volume&bdiitree_type=total_jobs&bdii_object=service&bdii_server=is-osg&start_type=7daysago&start_date=02%2F08%2F2012&end_type=now&end_date=02%2F08%2F2012&facility=on&facility_10009=on&gridtype=on&gridtype_1=on&active_value=1&disable_value=1).    

**What is the difference between gram2 and gram4 (i.e., between globus-job-run and globusrun-ws)?** 

According to [Globus](http://www.globus.org/)
  >"In WS GRAM, the globusrun-ws command implements the functionality of globusrun using the XML Job Description language in place of the RSL format job description of pre-WS GRAM. It also allows specifying parts of the Job Description with simple command line arguments (for executable and arguments), similar to what one would do with globus-job-run. Like globusrun, the globusrun-ws program supports both the interactive and batch submission of GRAM jobs."
[Read more...](http://www.globus.org/toolkit/docs/4.0/execution/wsgram/WS_GRAM_Migrating_Guide.html)    

**What happens if I run a "bazillion squillion" jobs on one site?**
  
  Please don't. If you do, you'll only do it once. Remember the sites control their resources, OSG doesn't. If you make the site administrators angry, their retribution may be visited upon you specifically, or on your entire VO. Then you've got a lot of angry people to deal with. See [Helpful Hints for Running At-Scale on the OSG](Documentation.GoldenRulesForOSGUsage).


About OSG's Software
--------------------

**What is the VDT?**
  
  The VDT is the underlying software distribution used by OSG sites and user to provide and access computing and storage across OSG. It attempts to be grid-agnostic and can be used by multiple grids. [Read more...](http://vdt.cs.wisc.edu/)

**What is the OSG Software Stack? How is it related to the VDT?**
  
  The OSG Software Stack is the subset of the VDT used by OSG sites. It also includes OSG-specific configuration such as hostnames of services running in OSG.

**What is Pacman?**
  
  [Pacman](http://physics.bu.edu/pacman/) is the package management tool that was used to install most of the OSG software stack prior to Release3. We now use yum and RPMs. See [yum and RPM basics](Documentation.Release3.YumRpmBasics).

**Why do you use Pacman instead of RPM?**
  
  Pacman provides some really nice features, such as the ability to install multiple versions at the same time and the ability to install software as non-root. That said, as of the writing of this answer (February 2010), we are working hard on providing the VDT as native packages, both RPM and Debian.   

**How is the OSG software validated before moving a new release to production?**
  
  All OSG software undergoes three levels of testing before releasing it to production. First, the VDT team tests software internally. Second, a small group of sites called the Validation Testbed (or VTB) tests the software. Finally, a larger group of cooperative sites called the Trash/Trash/Integration Testbed (or ITB) do testing along with VOs, who ensure their software continues to work correctly. Only once the ITB has given its stamp of approval can we release the software for production use.


Installation and Configuration of OSG Sites
-------------------------------------------

**What do I have to have in place before I setup an OSG resource?**
  
  See [Site Planning](Documentation.Release3.SitePlanning).    

**How do I make my site's resources available to OSG members?**
  
  OSG welcomes new resources! The basic installation of an OSG Compute Element or Storage Element requires that certain sets of hardware be available and configured with the OSG software. You will also need to determine your site's policies for usage. It is best to contact us (see [contacts](ContactsMailingLists) or you can dive into the [documentation](WebHome).    

**What should I name my OSG resource?**
  
  Each OSG resource needs a unique name by which services and resources may refer to the resource. This name will be displayed on the Site Catalog and used in tables for other monitoring and accounting. See [Resource Name](ReleaseDocumentation/ResourceName).

**How do I install an OSG compute element?**
  
  The OSG Computer Element (CE) software has several prerequisites for the platform and hardware. You will also need to understand the systems that you will be using for your CE and worker nodes, along with the network and firewall configuration for your site. Start with [Preparing Compute Element.](Documentation.Release3.PreparingComputeElement)    

**What should I install on my site's worker nodes?**
  
  There are a few options. See [Worker Node Client](Documentation.Release3.InstallWNClient).   

**Do I need to shut down and uninstall my Compute Element (CE) installations before I upgrade them?**
  
  You need to shutdown all services. See [Stopping Services](Documentation.Release3.InstallComputeElement#7_2_Stopping_and_Disabling_Servi). (Also, see the man page: `man vdt-control`.)    

**How should I configure local storage on my OSG compute element?**
  
  See [Local storage configuration](Documentation.Release3.LocalStorageConfiguration). How do I set up a BestMan based Storage Element? Please refer to the instructions on [Bestman](Documentation.Release3.InstallOSGBestmanSE).


Administration of OSG Sites
---------------------------

**How can I ensure that the next release of OSG software will run on my site?**
  
  We encourage you to participate in testing and validating the OSG software prior to its release. To do so, you need to participate in the Trash/Trash/Integration Test Bed (ITB) and attend the weekly integration meetings. For information about the ITB, see What is the integration grid and the Trash/Trash/Integration Contacts.

**How do I troubleshoot the edg-mkgridmap script?**
  
  See the [Edg Mkgridmap Troubleshooting Guide](Documentation.Release3.TroubleshootingComputeElement#TroubleshootingEdgMkgridmap)    

**How do I activate and deactivate my Resource on the OSG?**
  
  See the [How to register your resource with GOC](ReleaseDocumentation/ComputeElementPostInstall#Included_topic_Register_Resource).    

**How do I authorize users on a compute element?**
  
  OSG supports three of the available GUMS authorization scenarios: Grid3/Local, Compatibility, and Full Privilege. All three use the Virtual Organization Membership Service (VOMS). [Read more...](ReleaseDocumentation/AboutAuthorizationForCE)    

   
Security and Certificates
-------------------------

**What should I do if a security incident occurs?**
  
  If you believe a security incident has occurred with an OSG resource, please go to [Incident Discovery and Reporting](IncidentDiscoveryReporting), and report it **immediately**.        

**After a security incident, how do I (as a resource admin) ban a suspicious user?** 
  
  Currently, OSG software stack does not provide any banning tool. The security team is working to provide a banning tool this year. However, there are a few effective alternatives.

  First, if the suspicious user's certificate is revoked (this quite often happens in incidents), make sure that you have updated CRL lists from that CA. You can manually download the CRLs or run fetch-crl script provided by VDT. This is already installed in your VDT stack and typically under your installation directory. Once downloaded the CRLs will most likely be located in /etc/grid-security/certificates. This will ensure that at the authentication step, the suspicious user would fail and cannot access your grid resources. Of course, you have to ensure that your applications and resources/services also consult the CRLs during the authentication step.

  If the certificate is not revoked, you can remove the mapping for this user in your GUMS (see GUMS web page <https://www.racf.bnl.gov/Facility/GUMS/1.2/use_configuration.html>). Once the user's mapping is removed, the user's authorization with your site would fail. However, be careful that every 8 hours or so, your GUMS server synchronizes with VOMS servers. Therefore if the suspicious user is still listed as a member of a VO, your GUMS server would fetch the membership and create a mapping for this user. You can either remove the user's mapping every 8 hours from GUMS or create a special "null" mapping for the user in your GUMS. This null mapping should not be overwritten by the synchronization data.

**What is a grid certificate?**
  
  Grid certificates are ways to prove that you are who you claim to be when you attempt to use an OSG resource. These certificates are issued by a trusted source (e.g., the US Dept. of Energy) and require a password from you. In this way, they are similar to using ID cards such as your driver's license or passport. You must have a currently valid certificate that was issued from an approved Certificate Authority to use OSG resources. [Read more...](Documentation.CertificateWhatIs)    

**How do I get or renew a grid certificate for users of the OSG?**
  
  There is [How do I get a certificate for the OSG](Documentation.Release3.CertificateUserGet). Contact your Virtual Organization for what certificate authority is used within your group. To renew an unexpired certificate or replace an expired certificate, see [miscellaneous certificate tasks](Documentation/MiscellaneousCertificateTasks).    

**Can someone reset the password on my certificate key?**
  
  No. You are the only person who knows the password to your keys.   

**What are OSG users' responsibilities in keeping OSG resources secure?**
  
  As an OSG user, you are expected to:
    * Protect your grid identity token
    * Abide by the policies and procedures of your Virtual Organization (VO)
    * Report any known or suspected security breach
[Read more...](Documentation.SecuritySiteResponsibilities)    

**What are OSG resource administrators' and VO administrators' responsibilities in keeping OSG secure?** 
  
  As an admin, you are expected to:
    * Protect all grid identity tokens (personal, host, service)
    * Follow the [instructions for installing and configuring OSG software](Documentation.Release3.WebHome)
    * Abide by the policies and procedures of your Virtual Organization (VO)
    * Report any known or suspected security breach
[Read more...](Documentation/SecuritySiteResponsibilities)    

**What do I do if my root certificate expires?**
  
  You can fetch the new certificate, if available and import it into your trusted root CA directories. Please make sure that that you download the Digicert root and intermediate CA certs that are needed to add to the OS X Keychain (for example) or to the trusted issuer stores in the various browsers from [here](http://www.digicert-grid.com/). See [Install CA certificates in the browser](Documentation/CertificateGetWeb#InstallCaCert) for the entire procedure.

  If there is no new certificate, then you can remove the expired certificate from trusted CA directory. Since the CA is no longer serving, you do not trust the certificates issued by this CA.
   
**How do I update my GUMS service template?**
  
  This is discussed in [Installing and Configuring GUMS](ReleaseDocumentation/InstallConfigureAndManageGUMS). You will use the `gums-create-config` script.    

**How do I update my CA trusted directories?**
  
  There is a package to automatically update the trusted CA certificates begining with VDT 1.8 (OSG 0.8). See http://vdt.cs.wisc.edu/releases/2.0.0/certificate_authorities.html#vdt-update-certs

**My web browser does not trust the OSG CA?**
  
  See [Install CA certificates in the browser](Documentation/CertificateGetWeb#InstallCaCert) for a procedure to solve this problem.
