# Setting-up-NAS-Server

<img width="860" height="516" alt="NAS-Diagram" src="https://github.com/user-attachments/assets/92ab25f1-4377-48cd-b6e6-89a40be78d5b" />

A write-up of how I set up my NAS along with what I learned after completing the set up.

## Setup Steps:

1. Install the HDDs into the NAS bays
2. Turn over the NAS and install the SSD, and RAM inside the bottom panel
3. Connect the NAS to the switch with an Ethernet cable
4. Power on and find the NAS on the network
5. Create users and shared folders, and enable Samba (SMB) in the NAS settings
6. Reserve a fixed IP for the NAS in the router 

One Issue:
1. When I installed one of the hard drives, the NAS didn't detect it as working, so I returned the defective hard drive and bought a replacement. The new drive worked fine.

## My set up

| Component | Details |
| HDDs | [4 drives / 12TB] | <img width="3000" height="1389" alt="20261003_140512" src="https://github.com/user-attachments/assets/7c55e6f3-4348-4402-8f00-3f1194ecd3b0" />


| SSDs | [1 / 2TB] | <img width="3000" height="4000" alt="20261003_153140" src="https://github.com/user-attachments/assets/237e1df6-150e-4625-a513-14096a0f818e" />


| RAM | 32GB | <img width="4000" height="3000" alt="20261003_140720" src="https://github.com/user-attachments/assets/074280f0-7165-4c60-b15b-4a2554ff3bc1" />
| Switch | tp-link 5-Port Gigabit / speed | <img width="3000" height="4000" alt="20261003_140631" src="https://github.com/user-attachments/assets/aa50afdf-b4f7-4f20-83a3-c38b6b533ee3" />

| laptop | Linux Mint [version] ([Cinnamon/MATE/Xfce]) |  <img width="512" height="512" alt="linux-mint" src="https://github.com/user-attachments/assets/f5b5ae0e-8d7a-474b-9d4a-3373b81e1933" />


## Key Terms I learned about while doing this project :

Container - a light weight, isolated environment that runs an application along with everything it needs: code, libraries, and settings.

Docker - a platform for building, shipping, and running applications inside containers. 

Dynamic Host Configuration Protocol (DHCP) - is a network protocol that automatically assigns IP addresses and other network settings to devices when they connect. A DHCP server hands out an IP address, subnet mask, default gateway, DNS server addresses.

Hard Disk Drive (HDD) - traditional storage that saves data on spinning magnetic platters. Slower and noisier than an SSD, but much cheaper per terabyte, which makes it the standard choice for bulk storage like media libraries and backups. 

Network File System (NFS) - A Linux/Unix-native file-sharing protocol. It can be a little faster and simpler than samba between Linux machines, but SMB is better supported by default on a NAS.

Port Mapping - is a router setting that directs incoming network traffic on a specific port to a specific device inside your private network

Random Access Memory (RAM) - short term memory ten system uses for whatever it is working on. More RAM helps when running several apps, containers, or services at once. It is not storage, and its contents are cleared when the power goes off.

Router - A device that connects your local network to other networks, mainly the internet. It hands out IP addresses to your devices DHCP, decides where traffic should go, and usually includes a firewall.

Samba (SMB) - a free software that lets Linux/Unix computers share files and printers with Windows computers on a network. It implements Microsoft's SMB (Server Message Block) protocol, so a Linux machine running Samba can show up in Windows File Explorer as a regular shared folder, and Linux can also access Windows shares. It can even act as a Windows-style domain controller, handling logins for a network.

Server - a computer (or a program running on one) that provides a service or resources to other computers, called clients, over a network. The client sends a request, and a server responds.

Solid State Drive (SSD) - Storage with no moving parts that uses flash memory. Much faster and quieter than an HDD, but more expensive per terabyte. In a NAS, it is often used as a cache or for apps and databases that need quick access.

Switch - A device that connects multiple wired devices (laptop, NAS, TV, etc.) on the same local network so they can talk to each other. It forwards data only to the device it is meant for.

NAS - A NAS is a small always-on computer built to hold several drives and share their storage over your network. You can use it as a private cloud, a backup target, and a media server.


## Questions I was asking myself and learned while setting up the NAS:

1. Why using both router and switch?  
The switch provides the physical network lanes, and the router directs traffic on those lanes. The router decides where data needs to go (to another device at home, or out to the internet), while the switch gives all my wired devices enough ports to connect to the network.

2. Why not just switch?
A switch only provides the physical lanes. It allows data packets to physically travel back and forth between my laptop and NAS. But on its own it can't hand out IP addresses or connect me to the internet.

3. How are folder/files shared across different devices?
Through a file-sharing protocol.

4. How are applications on the NAS or other devices ran?
Through utilizing docker containers.

5. How to restrict access to my NAS?
By using a firewall.


