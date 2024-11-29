

# CTF 30 Days or 30 VM Machines to Hack
**Playlist**: If you want Walkthroughs, here is the creator responsible for the challenge. All credits go to them:  
[Watch the playlist here](https://www.youtube.com/watch?v=xnCS8fYfrjs&list=PLHBDBcFA_l_WBcUJWf8cp5BaPsUkquRQU)

This is not a **Walkthrough** or step-by-step guide. It's just a documentation that directs you on how to proceed, highlighting the logic behind CTF challenges or potential errors and obstacles. It helps adapt to personal needs and carve your own path, creating a mental map of the process.  

Additionally, you'll find options for alternative tools and a brief description of each one used. Every issue or obstacle I face will be documented here for reference.  

It's still messy, and I don't know if or when I'll tidy it up. But here it is—I hope it helps you somehow.

---

## VirtualBox Setup: Creating Your Virtual Network Lab
1. Navigate to **Tools → Properties → NATNetworks**.  
   Configure as follows:
   - **Name**: `<VMnet8>` (Create a name for your network)
   - **IPv4 Prefix**: `10.10.10.0/24` (Set address range)
   - Click **Apply**.

### Parrot / Kali (and other VMs)
2. Configure your VM:
   - **Settings → Network**  
     - **Adapter 1**: Enable Network Adapter  
       - **Attached to**: NAT Network  
       - **Name**: VMnet8 (The network you created)  
       - **Adapter Type**: Select your adapter.  
       - **Promiscuous Mode**: Deny (Enable only if testing WiFi networks).  
       - Check **Cable Connected**.  
   - Click **OK**.

Ensure all VMs in this lab are set to the same NAT network.  
For more about NAT networks in VirtualBox:  
- [NanoShots Guide](https://www.nanoshots.com.br/2015/08/virtualbox-configurando-o-acesso-ssh.html)  
- [VirtualBox Manual](https://www.virtualbox.org/manual/ch06.html)  

---

## Identifying Target in Your VM (Attacker)
Click the **Network Connection Information icon** or use `ifconfig` to see your IP and range.  
Example configuration: `10.10.10.0/24`.  

Use one of the following tools to identify active hosts:  
- `nmap -sn 10.10.10.0/24`  
- `fping -a -g 10.10.10.0/24`  
  - `-a`: Show active hosts  
  - `-g`: Specify range  
- `arp-scan --localnet`  
- `netdiscover -r 10.10.10.0/24`  
- `nbtscan -r 10.10.10.0/24`  

---

## Workflow Stages & Tools

### 1. Setup Instructions
Tools Used:
- **VirtualBox** or **VMware**: To create virtual machines.  
- **NAT Network Configuration**: For seamless interaction between local and virtual machines.  
- **File Sharing Tools**: WinSCP or Samba for transferring files.  
- **Traffic Analysis Tools**: Wireshark for capturing and analyzing packets.  

---

### 2. Reconnaissance (Recon)
Tools Used:
- **Nmap**: Port scans, service identification, and version detection.  
- **Masscan**: Rapid network scanning.  
- **Whois**: Retrieve domain and IP information.  
- **Sublist3r**: Enumerate subdomains.  
- **Dnsenum/Dnsmap**: DNS record scans.  
- **Gobuster/BfExploit**: Directory and file brute-forcing on HTTP servers.  
- **Nikto**: Web vulnerability scanner.  
- **Dirb/Dirbuster**: Brute-force tools for directory enumeration.  

---

### 3. Enumeration
Tools Used:
- **Hydra**: Brute-force tool for protocols like SSH, FTP, HTTP, etc.  
- **Nikto**: Web scanner for detecting application vulnerabilities.  
- **Nmap Scripts** (`-sC`): Service enumeration and vulnerability detection.  
- **Gobuster/Dirbuster**: Directory and file scanning.  
- Protocol brute-forcing examples:  
  - **FTP**: `hydra -l username -P password_list ftp://target`  
  - **SNMP**: `snmpwalk -v1 -c community_target 192.168.0.1`  

---

### 4. Vulnerability Identification
Tools Used:
- **Metasploit Framework**: Exploiting known vulnerabilities.  
- **CVE Exploits Database**: To find suitable exploits.  
- **SQLmap**: For SQL injection exploitation.  
- **Nessus/OpenVAS**: Vulnerability scanners.  
- **Wireshark**: Analyzing network traffic.  
- **Burp Suite**: Web vulnerability analysis (e.g., XSS, CSRF).  
- **Metasploit Auxiliary Modules**: Port and service scanners.  

---

### 5. Exploitation
Tools Used:
- **Metasploit Framework**: For exploitation modules like ProFTPD vulnerabilities.  
- **MS17-010 Exploit** (EternalBlue): Exploit SMB vulnerabilities.  
- **Empyre/Empire**: C2 frameworks for remote shell management.  
- **Veil-Evasion**: Create payloads to bypass detection.  
- **Powersploit**: PowerShell scripts for exploitation.  
- **Netcat (nc)**: Interaction with services.  

---

### 6. Privilege Escalation
Tools Used:
- **LinPEAS/WinPEAS**: Identify misconfigurations and permissions.  
- **GTFOBins**: Commands for privilege escalation on Linux.  
- **SUID3dump**: Find SUID binaries.  
- **Impacket**: Tools for lateral movement in Windows environments.  
- **Mimikatz**: Extract credentials and hashes.  

---

### 7. Post-Exploitation
Tools Used:
- **Metasploit Meterpreter**: Interactive remote shell.  
- **Cobalt Strike**: C2 Framework for automation.  
- **Mimikatz**: Credential extraction.  
- **Rubeus**: Kerberos ticket extraction.  
- **Ncat (nc)**: Persistent connections and data exfiltration.  

---

### 8. Flag Collection
Tools Used:
- **Cat**: Display text file contents.  
- **Find**: Locate relevant files.  
- **Strings**: Extract readable strings from binaries.  
Example Commands:  
- `cat /root/flag.txt`  
- `strings /usr/bin/flag_binary`  

---

### 9. Conclusion
- Summarize your successful exploitation process.  
- Document lessons learned and effective tools/techniques.  

---  
**Happy hacking!** 🎯  

shell -t /bin/bash

python -c "import pty; pty.spawn('/bin/bash')"  

python3 -c "import pty; pty.spawn('/bin/bash')"  correct

python3 -c 'import pty; pty.spawn(/"bin/bash")'

find / -perm -u=s -type f 2>/dev/null

find . -perm /6000


                                                              







   
