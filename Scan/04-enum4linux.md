## SMB Enumeration (enum4linux)

## Overview
Since ports 139/tcp & 445/tcp (SMB) are open, an enum4linux scan was conducted to gather information about the SMB services, including users, shares, and access permissions.

---

**Target:** 192.168.56.101
**Scan Type:** enum4linux -a

---

### Command Breakdown

- `-a` ->  Runs all enumeration checks on the target

---

### Key Findings

- SMB services do not allow anonymous (null session) access.
- No workgroup or domain information was revealed.
- NetBIOS enumeration did not return any results
- Without credentials, only limited information could be gathered.

---

### Observations

- Although the SMB services are exposed, they restrict anonymous enumeration which reduces our immediate information disclosure.
- The lack of accessible shares or user data suggests that the system has basic access controls in place.
- Further enumeration of the SMB services would likely require valid credentials or an alternative attack method.

---

## Raw Scan Output

```bash
┌──(kali㉿kali)-[~]
└─$ enum4linux -a 192.168.56.101
Starting enum4linux v0.9.1 ( http://labs.portcullis.co.uk/application/enum4linux/ ) on Sat May  2 00:05:15 2026

 =========================================( Target Information )=========================================

Target ........... 192.168.56.101
RID Range ........ 500-550,1000-1050
Username ......... ''
Password ......... ''
Known Usernames .. administrator, guest, krbtgt, domain admins, root, bin, none


 ===========================( Enumerating Workgroup/Domain on 192.168.56.101 )===========================


[E] Can't find workgroup/domain



 ===============================( Nbtstat Information for 192.168.56.101 )===============================                                               
                                                                            
Looking up status of 192.168.56.101                                         
No reply from 192.168.56.101

 ==================================( Session Check on 192.168.56.101 )==================================                                                
                                                                            
                                                                            
[E] Server doesn't allow session using username '', password ''.  Aborting remainder of tests.                                                          
                                                                            
                                                                            
