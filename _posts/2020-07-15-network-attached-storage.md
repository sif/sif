---
layout: post
title: "Network-Attached Storage"
categories: hardware
tags: hardware NAS
---

* TOC
{:toc}

<a href="https://www.afterlifesong.com/files/Digital_Asset_Security_Checklist_enu.pdf">Digital_Asset_Security_Checklist_enu.pdf</a>

## Reasons to Buy

- Data redundancy (resistance to data loss from one hard drive failure)
- Backup (another copy data)
  - Every storage uses different material, for example, CD may last around 2 to 8 years but it's unreliable due to its cheap construction, Blu-ray may last around 50 years but it's often small (25 GB for single layer, 50 GB for dual layer)
  - A NAS will often use the best in class construction that often border enterprise level hard drive, in fact, often is the same hard drive most small to medium size businesses uses 
- Data life
- Ability to access data remotely
- Large storage
- Separation of storage from process
- Inexpensive
- Basically acts as a small server
- Ability to stream data
- Ability to share data
- Form your own cloud/internet
- Easy to setup, easy to transfer
- Important and useful enough that home burglars will steal this first thing first, that's why there are ways to lock it down including physical lock and encryption

Important: reliable, simplicity, valuable



## Synology

http://literatitech.blogspot.com/2011/06/those-annoying-eadir-files-synology.html

https://kb.synology.com/en-global/DSM/tutorial/file_or_folder_name_displayed_as_12HWA0_8

https://mixable.blog/synology-how-do-i-update-an-existing-docker-container-with-a-new-image/

iperf (NAS to windows speed test)
librespeed in docker (NAS to net)



### DSM

https://kb.synology.com/en-au/DSM/tutorial/What_stops_my_Synology_NAS_from_entering_System_Hibernation

Go here to change how long it takes before napping:
DSM -> Control Panel -> Hardware & Power -> HDD Hiberation



### Self-Hosting



#### Vaultwarden

To install Vaultwarden:

- Make sure there is a directory for Vaultwarden to store the passwords and Vaultwarden is installed on the Docker via the Registry. Use the 'latest' tag.
- Launch it via Image. Go to Advanced Settings. 
- Select "Enable auto-restart". In Volume, add folder. Select the folder that was created in the first step. For Mount path, type "/data".
- Apply, "Next". "Run this container after the wizard is finished". "Done".

Vaultwarden should now work. Launch it via a browser.

### Hardening

https://www.synology.com/en-us/knowledgebase/DSM/tutorial/Management/How_to_add_extra_security_to_your_Synology_NAS

analogy:

- ipblock = fail2ban
- firewall = iptables



#### Firewall

Control Panel -> Firewall

Problem with firewall on the NAS is that it is possible to permanently lock yourself out

you could just block based on georegion

just select the countries with the most scammers and hostile to us

ensure that private IPv4 range is used:

```
10.0.0.0 - 10.255.255.255
172.16.0.0 - 172.31.255.255
192.168.0.0 - 192.168.255.255
```

**default**



**custom** (current, active)

I do recommend creating a different firewall profile



#### IP Block

Control Panel -> Protection -> Allow/Block List

this Allow/Block List only deals with login attempts



#### Exposure

Make sure Control Panel > QuickConnect is disabled. Make sure the three tabs in Control Panel > External Access are blank.



#### No Local Access Without Internet

You should have access to your Synology but if you don't.. it's usually the router, ping the router via gateway



#### Permissions

checking folder permission: File Station -> Properties -> Permission -> administrators, Allow, Read & Write



### DS220j

Only good for storage and that's about it


