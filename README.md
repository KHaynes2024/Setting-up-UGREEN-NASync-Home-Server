# Setting-up-UGREEN-NASync-Home-Server

A write-up of how I set up my home server along with key definitions. I also added some questions I had along the way.

## Key Terms

UGREEN NASync - UGREENS's line of Network Attached Storage (NAS) devices. A NAS is a small always-on computer built to hold several drives and share their storage over your network. You can use it as a private cloud, a backup target, and a media server.

Hard Disk Drive (HDD) - traditional storage that saves data on spinning magnetic platters. Slower and noisier than an SSD, but much cheaper per terabyte, which makes it the standard choice for bulk storage like media libraries and backups. 

Solid State Drive (SSD) - Storage with no moving parts that uses flash memory. Much faster and quieter than an HDD, but more expensive per terabyte. In a NAS, it is often used as a cache or for apps and databases that need quick access.

Random Access Memory (RAM) - short term memory ten system uses for whatever it is working on. More RAM helps when running several apps, containers, or services at once. It is not storage, and its contents are cleared when the power goes off.

Switch - A device that connects multiple wired devices (laptop, NAS, TV, etc.) on the same local network so they can talk to each other. It forwards data only to the device it is meant for.

Router - A device that connects your local network to other networks, mainly the internet. It hands out IP addresses to your devices (DHCP // add DHCP as a term please), decides where traffic should go, and usually includes a firewall.

Network File System (NFS) - A Linux/Unix-native file-sharing protocol. It can be a little faster and simpler than samba between Linux machines, but SMB is better supported by default on a NAS.

Mount - Linux's way of making a drive or network share appear as a normal folder. I mount my NAS shares under '/mnt/nas/' (Kelli did you do this already or no ?), so they behave like any other directory.

## Questions I had:

1. Why using both router and switch?  
The switch provides the physical network lanes, and the router directs traffic on those lanes. The router decides where data needs to go (to another device at home, or out to the internet), while the switch gives all my wired devices enough ports to connect to the network.

2. Why not just switch?
A switch only provides the physical lanes. It allows data packets to physically travel back and forth between my laptop and NAS. But on its own it can't hand out IP addresses or connect me to the internet.

## My steup

| Component | Details |
| NAS | 'UGREEN NAS' |
| HDDs | [4 drives / 12TB] |
| SSDs | [1 / 2TB] |
| RAM | amount |
| Switch | tp-link 5-Port Gigabit / speed |
| Router | [model] |
| laptop | Linux Mint [version] ([Cinnamon/MATE/Xfce]) |

## Setup Steps:

1. Install the HDDs into the NAS bays
2. Turn over the NAS and install the SSD, and RAM inside the bottom panel
3. Connect the NAS to the switch with an Ethernet cable
4. Power on and find the NAS on the network
5. Create users and shared folders, and enable SMB in the NAS settings// chris comment ( we have not done that  yet / also descibe what SMB does on a plain levvel )
6. Reserve a fixed IP for the NAS in the router //chris comment (we have not done this yet)
