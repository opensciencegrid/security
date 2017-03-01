**Secure Email in OSG**
=======================


About This Document
-------------------

This document covers using secure email when communicating with the OSG security team. The OSG Security team encourages the use of secure email communication. All official announcements from the OSG security team will be digitally signed. We encourage you to verify the digital signatures on OSG security announcements. Also when sending sensitive information to the OSG security team, we encourage you to encrypt your messages.

News
----

-   2010-01-28: The OSG security team has updated the PGP key for <security@opensciencegrid.org>.

OSG Security PGP key
--------------------

``` file
User ID: Open Science Grid Security <security@opensciencegrid.org>
Key ID: 7FD42669
Expires:  
Fingerprint: 6E5F 4DD8 7ABC 9F68 A49B  F3CA 15E3 B3AD 7FD4 2669
```

The team key is available from the [Security Team Members](SecurityTeamMembers) page or the [MIT PGP server](http://pgp.mit.edu:11371/pks/lookup?search=security%40opensciencegrid.org&op=index). PGP software is available from: [GnuPG](http://www.gnupg.org/)

Verifying a PGP signature
-------------------------

1. Install [GnuPG](http://www.gnupg.org/) if it is not already installed on your computer.

2. Save [osg-security-pubkey.asc](https://twiki.grid.iu.edu/twiki/pub/Security/SecurityTeamMembers/osg-security-pubkey.asc) to a file on your computer.

3. Import the <security@opensciencegrid.org> public key:

``` screen
[user@client ~]$ gpg --import < osg-security-pubkey.asc 
gpg: key 7FD42669: public key "Open Science Grid Security <security@opensciencegrid.org>" imported
gpg: Total number processed: 1
gpg:               imported: 1
```

4. Save the message you want to verify to a file on your system (for example: [signed-message.txt](https://twiki.grid.iu.edu/twiki/bin/viewfile/Documentation/SecureEmail/signed-message.txt)).

5. Verify the message:

``` screen
[user@client ~]$ gpg --verify < signed-message.txt 
gpg: Signature made Tue Apr 14 13:18:26 2010 CDT using DSA key ID 7FD42669
gpg: Good signature from "Open Science Grid Security <security@opensciencegrid.org>"
```

To verify additional messages, only steps 4-5 are required.

When the <security@opensciencegrid.org> public key expires, you will need to perform steps 2-3 again for the new public key.

Encrypting a PGP message
------------------------

1. Install [GnuPG](http://www.gnupg.org/) if it is not already installed on your computer.

2. Save [osg-security-pubkey.asc](https://twiki.grid.iu.edu/twiki/bin/viewfile/Security/SecurityTeamMembers/osg-security-pubkey.asc) to a file on your computer.

3. Import the <security@opensciencegrid.org> public key:

``` screen
[user@client ~]$ gpg --import < osg-security-pubkey.asc 
gpg: key 7FD42669: public key "Open Science Grid Security <security@opensciencegrid.org>" imported
gpg: Total number processed: 1
gpg:               imported: 1
```

4. Save the message you want to encrypt to a file on your system named message.txt.

5. Encrypt the message:

``` screen
[user@client ~]$ gpg --recipient security@opensciencegrid.org -a --encrypt < message.txt > encrypted-message.txt
```

6. Send the encrypted-message.txt file in email to <security@opensciencegrid.org>.

To encrypt additional messages, only steps 4-6 are required.

When the <security@opensciencegrid.org> public key expires, you will need to perform steps 2-3 again for the new public key.

Other PGP Clients
-----------------

### Enigmail OpenPGP plugin for Thunderbird

The OpenPGP plugin for [Thunderbird](http://www.mozillamessaging.com/en-US/thunderbird/) provides a well integrated user interface for key management and email signing and verification that uses GnuPG underneath.

Signing an S/MIME message with your certificate
-----------------------------------------------

The following is a command line instruction on how to sign an email with your certificate. Instructions for web clients is below.

``` screen
[user@client ~]$ openssl smime -sign -signer ~/.globus/usercert.pem -inkey ~/.globus/userkey.pem -in message.txt | mail -s "email subject" person@example.com
```

-   message.txt - body of the email message
-   ~/.globus/usercert.pem, userkey.pem - your personal grid certificate
-   <person@example.com> - address where email is to be sent

Alternatively, you can send message.txt as an attachment with nearly any email client. It generally works better to send the signed file as an attachment rather than copying it into the body of the message because various email clients and particularly web interfaces to email often modify the message body and therefore break the digital signature.

### Email client instructions

With the diversity of different web and various mail clients it is difficult to keep instructions up-to-date on how to deal with certificates. So below we link to a few different sites that deal in X509 certificates and have good instructions on signing emails, as well as other topics dealing with certificates.

[Thawte's how to sign an email instructions.](https://search.thawte.com/support/ssl-digital-certificates/index?page=content&id=SO1732)

[Verisign certificate instructions.](https://knowledge.verisign.com/support/digital-id-support/index?page=content&id=AR654)

Verifying an S/MIME signed message
----------------------------------

``` screen
[user@client ~]$ openssl smime -verify -in message.txt -CApath $X509_CERT_DIR -signer sendercert.pem
[user@client ~]$ openssl x509 -in sendercert.pem -noout -subject -email -serial -dates
```

-   `message.txt` - body of email message received
    -   note that the line beginning "Content-Type" and including 'boundary="---' must be a single line and not get broken or wrapped.
-   `sendercert.pem` - the certificate used by the sender to sign the message, is extracted with the openssl smime command
-   `openssl x5091` command above will display the subject, email address, serial number and validity dates of the signer's certificate

