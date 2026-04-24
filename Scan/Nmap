## Nmap Scan Results
**Target:** 192.168.56.101
**Scan Type:** nmap -sV

---

### Open Ports

- **21/tcp** - FTP (vsftpd 2.3.4)
- **22/tcp** - SSH 
- **23/tcp** - Telnet
- **25/tcp** - SMTP
- **53/tcp** - DNS
- **80/tcp** - HTTP
- **111/tcp** - RPCBind
- **139/tcp** - NetBiOS-ssn
- **445/tcp** - NetBiOS-ssn
- **512/tcp** - exec
- **513/tcp** - login
- **514/tcp** - SHELL
- **1099/tcp** - java-rmi
- **1524/tcp** - bindshell
- **2049/tcp** - NFS
- **2121/tcp** - FTP
- **3306/tcp** - MYSQL
- **5432/tcp** - postgresql
- **5900/tcp** - VNC
- **6000/tcp** - X11
- **6667/tcp** - IRC
- **8009/tcp** - ajp13
- **8180/tcp** - HTTP

---

### Observations

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

