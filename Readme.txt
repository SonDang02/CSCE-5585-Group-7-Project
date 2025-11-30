Secure Network Implementation and Design.


In this project, the design and configuration of a secure network environment based on GNS3, FortiGate firewall, Suricata, Wireshark, and Nessus are shown. It includes segmentation of the network, VPN configuration, deployment of IDS/IPS, simulating attacks and vulnerability testing.


Project Overview


This project will aim at developing a robust network architecture that will integrate:


 Separation of DMZ and LAN.
 Traffic filtering and firewall rules.
 Remote Access VPN
 IDS/IPS detection and prevention.
 SYN flood attack simulation
 Host-level and Network vulnerability tests.


Technologies Used


 GNS3
 FortiGate Firewall (v7.0.9)
 Ubuntu Server & Clients
 Kali Linux
 Suricata
 Wireshark
 Nessus


Network Architecture


The topology includes:


 Public facing services DMZ network.
 Private LAN network
 FortiGate firewall to do routing, segmentation VPN, and IPS.
 External user remote access.
 host-based monitoring and detection IPS/IDS.


Firewall Policies


Traffic rules implemented:


Allowed:


 LAN to DMZ
 LAN to Internet
 DMZ to Internet
 Remote VPN users to LAN


Blocked:


 DMZ to LAN (to avoid internal network being exposed)


VPN Remote Access


A remote access VPN was set up to enable authenticated user to have access to the LAN. The VPN uses the IPs of the range 10.10.10.1-10.10.10.10, making sure that the internal resources are secured.


Attack Simulation/IDS/IPS.


To simulate a SYN flood attack with a Kali machine was done using:


sudo hping3 -S -p 80 -i u10000 <victim-ip>


Wireshark was used to identify the attack on the Ubuntu client. Suricata was tuned with tailored rules and it was able to block the repetitive SYN packets by the attacker, which proved to be effective host-based IDS/IPS.


Vulnerability Assessment


Nessus scan revealed some weaknesses at the host level and the network vulnerabilities which included:


 Old version of Ubuntu packages and end of life OS.
 Weak SSH algorithms
 Response to ICMP Time stamp requests disclosing system data.


Mitigation was done through updating packages, disabling weak algorithms, filtering ICMP timestamps and system hardening practice.


Conclusion


The project shows a safe network structure where there is effective segmentation, firewall policy, VPN access control, IDS /IPS detection and prevention, and vulnerability management. All these methods emphasize the need to have multi-level security and regular service of systems.