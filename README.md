
# CTF 30 days or 30 maq VM to hacker.

## Virtual Box Setupt : Creating your virtual network lab 

- Tolls => Properties => NATNetworks
General Options:
Name: <VMnet8> 'Created a name for your network'
IPv4 Prefix: 10.10.10.0/24 'Conf. address rang'
Apply.

## Parrot / Kali et. 
- Settings => Network
Adpter 1 => Enable Network Adapter:
Attached to: Nat Network
Name: VMnet8 'The Network you created'
Adpter Type: choose your adpter.
Promiscuous Mode: Deny ' Just allow if you might to test wifi-network'
check Cable Connected.
Ok.
You need to settup all VM for this lab the same 'NAT'your criate. 
Read morde About natwork on VM.

- https://www.nanoshots.com.br/2015/08/virtualbox-configurando-o-acesso-ssh.html
- https://www.virtualbox.org/manual/ch06.html

- Find Target on your VM 'Attacker'

# !!! Click Connection Informatio on icon Network or use ifconfig !!! You see your IP and ranger, in my case I configured to 10.10.10.0/24

- Nmap -sn <10.10.10.0/24>
- fping -a -g <10.10.10.0/24>
 -a (activi) -g (ranger)
- arp-scan --localnet
- netdiscover -r <10.10.10.0/24>
- nbtscan -r <10.10.10.0/24>
  


## Documentação das etapas de resolução do CTF ##

## 01 - Hacker Fest: 2019
https://www.vulnhub.com/entry/hacker-fest-2019,378/

## 02 - Pentester Lab: S2-052 
https://www.vulnhub.com/entry/pentester-lab-s2-052,206/
need to created a VM and used ISO as disk

## 03 - Droopy: v0.2
https://www.vulnhub.com/entry/droopy-v02,143/

## 04  `digitalworld.local: JOY`. 

- https://www.vulnhub.com/entry/digitalworldlocal-joy,298/
- set VM your NAT lab.

### 1. Reconhecimento (Recon)
1. Execute uma varredura com Nmap para identificar portas abertas.
   ```bash
   nmap -sV -v -Pn  <host> / nmap -sC -A -p- -Pn <host>

-Resultado da Varredura - 
   PORT    STATE SERVICE     VERSION
21/tcp  open  ftp         ProFTPD
22/tcp  open  ssh         Dropbear sshd 0.34 (protocol 2.0)
25/tcp  open  smtp        Postfix smtpd
80/tcp  open  http        Apache httpd 2.4.25
110/tcp open  pop3        Dovecot pop3d
139/tcp open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
143/tcp open  imap        Dovecot imapd
445/tcp open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
465/tcp open  smtp        Postfix smtpd
587/tcp open  smtp        Postfix smtpd
993/tcp open  ssl/imaps?
995/tcp open  ssl/pop3s?

Service Info: Hosts: The,  JOY.localdomain, 127.0.1.1, JOY; OS: Linux; CPE: cpe:/o:linux:linux_kernel


2. Enumeração

1. 
   
