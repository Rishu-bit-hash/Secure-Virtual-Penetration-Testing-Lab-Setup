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








