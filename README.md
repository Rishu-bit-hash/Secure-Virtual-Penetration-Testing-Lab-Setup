# Secure-Virtual-Penetration-Testing-Lab-Setup
A secure and isolated virtual penetration testing environment built with Kali Linux, Metasploitable 2, and Oracle VirtualBox for cybersecurity learning and ethical hacking practice.


## Project Overview
This project documents the design and deployment of an isolated, secure virtual penetration testing environment. The lab is built to safely conduct vulnerability assessments, network scanning, and penetration testing methodologies without risking exposure to the host machine or external production networks. 
The architecture consists of an attacking machine (Kali Linux) and a deliberately vulnerable target machine (Metasploitable 2) operating inside a strictly contained sandbox network.

## Lab Architecture & Network Design
The lab uses a private *NAT Network* configuration inside Oracle VirtualBox. This ensures that while both virtual machines can communicate with each other, all attack traffic is entirely contained within the hypervisor and cannot leak out to the local physical network or the public internet.

* *Hypervisor:* Oracle VirtualBox
* *Attacker Machine:* Kali Linux (Rolling Edition)
* *Target Machine:* Metasploitable 2 (Linux-based vulnerable appliance)
* *Network Type:* Isolated NAT Network 
* *Subnet Range:* 10.0.2.0/24
  
## Deployment & Configuration Steps
### Step 1: Virtual Network Creation
1. Opened VirtualBox and navigated to *Tools* -> *Network* -> *NAT Networks*.
2. Set the Network CIDR to 10.0.2.0/24 and enabled the *DHCP* service to automatically assign IP addresses to the virtual machines.

### Step 2: Virtual Machine Provisioning
* *Kali Linux:* Imported the official pre-built VirtualBox OVA file. Allocated 2 vCPUs and 2GB RAM.
* *Metasploitable 2:* Created a new Linux VM profile and attached the Metasploitable.vmdk virtual hard disk. Allocated 1 vCPU and 512MB RAM.

### Step 3: Network Interface Mapping
For both virtual machines, the network adapter settings were modified to ensure proper isolation:
1. Navigated to VM *Settings* -> *Network*.
2. Changed *Attached to:* from NAT to *NAT Network*.

## Connectivity Verification
To verify that the network isolation was successful and the machines could communicate properly, network reconnaissance commands were executed from the attacking machine.

### 1. IP Address Discoveries
* *Kali Linux IP:*  10.0.2.8
* *Metasploitable 2 IP:*  10.0.2.7
### 2. Ping Test Verification
A ping test was performed from the Kali Linux machine to the Metasploitable 2 machine to verify that both systems could communicate with each other over the network.
```bash
ping -c 4 10.0.2.7
```

## Screenshots Attached

1. IP Address Discovery and Successful Ping Test
   
<img width="1917" height="605" alt="Kali successfull ping Test" src="https://github.com/user-attachments/assets/90b02d46-6110-4311-8844-b6b44e240b47" />

2. VirtualBox VM List – Showing
•	Kali Linux
•	Metasploitable 2

<img width="1917" height="670" alt="VM List in VirtualBox" src="https://github.com/user-attachments/assets/a5d81721-fc3f-451b-9c4d-840b1901f2bc" />

3. Metasploitable 2 Running
   
<img width="1917" height="771" alt="Metasploitable 2 Running" src="https://github.com/user-attachments/assets/84290989-8b70-4b85-9efd-b017a6d6388b" />

## Key Learnings and Outcomes
Setting up the virtualized penetration testing environment involved learning key concepts of virtualization and networking, along with troubleshooting configuration issues to establish successful communication between the virtual machines.
•	Configured both Kali Linux and Metasploitable 2 virtual machines on a shared VirtualBox NAT Network to enable secure communication within an isolated testing environment.
•	Identified and verified the IP addresses assigned to each virtual machine using Linux networking commands such as ip a and ifconfig.
•	Performed ICMP echo request (ping) tests between the systems to confirm successful network connectivity and packet exchange.
•	Analyzed ping responses, including packet transmission and reception statistics, to ensure reliable communication between the virtual machines.
•	Verified that the lab environment was correctly configured and ready for subsequent penetration testing and security assessment activities.

## Conclusion
The virtual penetration testing lab was successfully deployed using Oracle VirtualBox, Kali Linux, and Metasploitable 2. Network isolation was achieved through a dedicated NAT Network configuration, ensuring a secure environment for cybersecurity experimentation. Successful connectivity testing confirmed that the lab is fully operational and ready for future activities such as network scanning, vulnerability assessment, service enumeration, and penetration testing exercises.









