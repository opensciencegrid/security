# Secure communications in OSG

This document covers using secure email when communicating with the OSG security team. The OSG Security team encourages the use of secure email communication. All official announcements from the OSG security team will be digitally signed. We encourage you to verify the digital signatures on OSG security announcements. Also when sending sensitive information to the OSG security team, we encourage you to encrypt your messages.

## OSG Security PGP Key
``` file
User ID: Open Science Grid Security <security@opensciencegrid.org>
Key ID: 7FD42669
Expires:  
Fingerprint: 6E5F 4DD8 7ABC 9F68 A49B  F3CA 15E3 B3AD 7FD4 2669
```

The team key is available from the [Security Team Members](SecurityTeamMembers) page or the [MIT PGP server](http://pgp.mit.edu:11371/pks/lookup?search=security%40opensciencegrid.org&op=index). PGP software is available from: [GnuPG](http://www.gnupg.org/)


## Generating a PGP signature for a message
1. Install [GnuPG](https://www.gnupg.org/) if it is not already installed on your computer.

## Verifying a PGP signature 
1. Install [GnuPG](https://www.gnupg.org/) if it is not already installed on your computer.
2. Save [osg-security-pubkey.asc](pgpkey/osg-security-pubkey.asc) to a file on your computer.
3. Import the security@opensciencegrid.org public key:
```
[user@client ~]$ gpg --import < osg-security-pubkey.asc 
gpg: key 7FD42669: public key "Open Science Grid Security <security@opensciencegrid.org>" imported
gpg: Total number processed: 1
gpg:               imported: 1
```
4. Verify the message (saved in signed-message.txt)
```
[user@client ~]$ gpg --verify < signed-message.txt 
gpg: Signature made Tue Apr 14 13:18:26 2010 CDT using DSA key ID 7FD42669
gpg: Good signature from "Open Science Grid Security <security@opensciencegrid.org>"
```

