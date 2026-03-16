# Red Team Recon Baseline — Metasploitable + Mac

**Date:** 2026-03-16  
**Operator:** Duk3  
**Scope:** Authorized lab targets only

## Targets
- Metasploitable (lab): `192.168.56.102`
- Personal Mac (authorized self-scan): `10.0.0.200`

## Methodology (high level)
- Nmap baseline scan (top ports, version detection)
- Evidence saved under `evidence/before/`

## Findings — Metasploitable (192.168.56.102)
### Open ports (from `evidence/before/metasploitable/nmap_top100.txt`)
21/tcp   open  ftp         syn-ack ttl 64 vsftpd 2.3.4
22/tcp   open  ssh         syn-ack ttl 64 OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)
23/tcp   open  telnet      syn-ack ttl 64 Linux telnetd
25/tcp   open  smtp        syn-ack ttl 64 Postfix smtpd
53/tcp   open  domain      syn-ack ttl 64 ISC BIND 9.4.2
80/tcp   open  http        syn-ack ttl 64 Apache httpd 2.2.8 ((Ubuntu) DAV/2)
111/tcp  open  rpcbind     syn-ack ttl 64 2 (RPC #100000)
139/tcp  open  netbios-ssn syn-ack ttl 64 Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open  netbios-ssn syn-ack ttl 64 Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
513/tcp  open  login       syn-ack ttl 64 OpenBSD or Solaris rlogind
514/tcp  open  shell       syn-ack ttl 64 Netkit rshd
2049/tcp open  nfs         syn-ack ttl 64 2-4 (RPC #100003)
2121/tcp open  ftp         syn-ack ttl 64 ProFTPD 1.3.1
3306/tcp open  mysql       syn-ack ttl 64 MySQL 5.0.51a-3ubuntu5
5432/tcp open  postgresql  syn-ack ttl 64 PostgreSQL DB 8.3.0 - 8.3.7
5900/tcp open  vnc         syn-ack ttl 64 VNC (protocol 3.3)
6000/tcp open  X11         syn-ack ttl 64 (access denied)
8009/tcp open  ajp13       syn-ack ttl 64 Apache Jserv (Protocol v1.3)
### Notes / observations
- Service exposure summary:
- Interesting versions/banners:
- Potential next recon steps (safe): service-specific enumeration

## Findings — Mac (10.0.0.200)
### Open ports (from `evidence/before/mac/nmap_top50.txt`)
49152/tcp open  unknown syn-ack ttl 64

### Notes / observations
- Likely services:
- Anything unexpected:
- Hardening candidates (if desired): firewall / sharing / ssh config

## Evidence files
- `evidence/before/metasploitable/nmap_top100.txt`
- `evidence/before/mac/nmap_top50.txt`

## Next steps
- Run focused scans on only open ports (-p list) with `-sC -sV` (safe default scripts)
- Optional: web fingerprinting if HTTP(S) is open (WhatWeb)
- Start “after” baseline once any hardening is applied (for Mac) or once lab changes are made

## Focused Enumeration — Metasploitable
### Targeted scan evidence
- `evidence/before/metasploitable/nmap_targeted.txt`

### Key service notes (fill in)
- FTP:
- SSH:
- HTTP:
- SMB:
- Database (if any):
