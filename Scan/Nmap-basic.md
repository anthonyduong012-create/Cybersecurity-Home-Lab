## Nmap Scan Results

## Overview
An initial Nmap scan was conducted to identify open ports and active services on the target system.

**Target:** 192.168.56.101
**Scan Type:** nmap -sV

---

## Command Breakdown
- `-sV` -> Detects service versions

---

### Open Ports

| Port | Service | Version/Name | Description |
|------|--------|--------------|------------|
| 21   | FTP    | vsftpd 2.3.4 | File transfer service; version is known to have a backdoor vulnerability |
| 22   | SSH    | OpenSSH      | Secure remote login and command execution |
| 23   | Telnet | telnetd      | Unencrypted remote access (insecure) |
| 25   | SMTP   | Postfix      | Handles sending email between servers |
| 53   | DNS    | BIND         | Resolves domain names to IP addresses |
| 80   | HTTP   | Apache       | Web server hosting websites/applications |
| 111  | RPCBind | rpcbind     | Maps RPC services to ports (used by NFS) |
| 139  | NetBIOS | netbios-ssn | Windows file/printer sharing (legacy) |
| 445  | SMB    | netbios-ssn  | Network file sharing; common attack target |
| 512  | exec   | rexecd       | Remote command execution (insecure r-service) |
| 513  | login  | rlogin       | Remote login service (insecure) |
| 514  | shell  | rshd         | Remote shell access (insecure) |
| 1099 | Java RMI | grmiregistry | Java remote method invocation service |
| 1524 | bindshell | root shell | Backdoor shell access (intentionally vulnerable) |
| 2049 | NFS    | nfs          | Network file system for file sharing |
| 2121 | FTP    | ProFTPD      | Alternate FTP service |
| 3306 | MySQL  | mysql        | Database service for storing application data |
| 5432 | PostgreSQL | postgres | Relational database service |
| 5900 | VNC    | vnc          | Remote desktop access |
| 6000 | X11    | X server     | Linux graphical display service |
| 6667 | IRC    | UnrealIRCd   | Internet Relay Chat service |
| 8009 | AJP13  | Apache JServ | Connector between web server and Tomcat |
| 8180 | HTTP   | Tomcat       | Web server for Java applications |

---

### Observations

- The system is exposed to many open ports and insecure services, leaving it extremely vulnerable.
- FTP service port 21 (vsftpd 2.3.4) is known to contain a backdoor vulnerability.
- Telnet (port 23) and r-services (port 512-514) transmit data in plaintext making it insecure.
- Multiple open database services ( MYSQL on 3306 and PostgreSQL on 5432) are potential access points for attackers.
- Web services (port 80 and 8180) may host vulnerable applications that can be exploited.

---
### Raw Scan Output
```bash
┌──(kali㉿kali)-[~]
└─$ nmap -sV 192.168.56.101
Starting Nmap 7.98 ( https://nmap.org ) at 2026-04-23 22:41 -0400
mass_dns: warning: Unable to determine any DNS servers. Reverse DNS is disabled. Try using --system-dns or specify valid servers with --dns-servers
Nmap scan report for 192.168.56.101
Host is up (0.029s latency).
Not shown: 977 closed tcp ports (reset)
PORT     STATE SERVICE     VERSION
21/tcp   open  ftp         vsftpd 2.3.4
22/tcp   open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)
23/tcp   open  telnet      Linux telnetd
25/tcp   open  smtp        Postfix smtpd
53/tcp   open  domain      ISC BIND 9.4.2
80/tcp   open  http        Apache httpd 2.2.8 ((Ubuntu) DAV/2)
111/tcp  open  rpcbind     2 (RPC #100000)
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
512/tcp  open  exec        netkit-rsh rexecd
513/tcp  open  login
514/tcp  open  shell       Netkit rshd
1099/tcp open  java-rmi    GNU Classpath grmiregistry
1524/tcp open  bindshell   Metasploitable root shell
2049/tcp open  nfs         2-4 (RPC #100003)
2121/tcp open  ftp         ProFTPD 1.3.1
3306/tcp open  mysql       MySQL 5.0.51a-3ubuntu5
5432/tcp open  postgresql  PostgreSQL DB 8.3.0 - 8.3.7
5900/tcp open  vnc         VNC (protocol 3.3)
6000/tcp open  X11         (access denied)
6667/tcp open  irc         UnrealIRCd
8009/tcp open  ajp13       Apache Jserv (Protocol v1.3)
8180/tcp open  http        Apache Tomcat/Coyote JSP engine 1.1
MAC Address: 08:00:27:7E:1A:33 (Oracle VirtualBox virtual NIC)
Service Info: Hosts:  metasploitable.localdomain, irc.Metasploitable.LAN; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

