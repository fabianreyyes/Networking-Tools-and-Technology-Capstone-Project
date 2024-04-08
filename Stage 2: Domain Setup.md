# Stage 2- Domain Setup

In this stage we added a Windows2012r2 server and connected it to our LAN-SWITCH to serve as our domain controller.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/endingtopologys2.png)
## Prepare a Win2012r2 server

Updated network adapter IP addresses, conducted ping tests to verify connectivity with remote destinations on WAN, LAN, and DNS networks. Configured and synchronized NTP (Network Time Protocol) settings. Renamed Host/Computer to DC (Domain Controller). Completed a system reboot and verified changes for functionality and accuracy.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/networkadapter.png)

## Install Active Directory

AD guide: https://learn.microsoft.com/en-us/archive/technet-wiki/22622.building-your-first-domain-controller-on-2012-r2

Deployed Active Directory services and configured the computer/domain name to **"domaincontroller"** (Note: Instrctions stated to name it localdomain). Executed a system reboot. Subsequently, initiated the promotion process to elevate the configuration to domain controller status. After completion, performed another system reboot to finalize the configuration changes.

## Create new AD users

On DC we establish user and administrative credentials for individual team members and the senior engineer. Incorporated administrative users into the domain administrators group to grant elevated privileges and access levels within the domain architecture.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/addusrs.png)

## Join Win10 to the widgets.localdomain domain.

On the Win10 workstation, the hostname was modified to "win10" followed by a system reboot to apply the changes. The primary DNS server was then configured to point to the IP address of the DC (Domain Controller). NTP settings were adjusted to synchronize with "dc.widgets.domaincontroller" (incorrect domain name but proceeded). Subsequently, the Win10 workstation was joined to "widgets.domaincontroller" (incorrect name but proceeded). Accessing the computer name/domain changes, the network was switched from a workgroup to a domain. During the process, login attempts were met with error messages prompting password changes. To resolve, the Win2012r2 server (Domain Controller) was accessed, logging in with a newly created admin account to reset the password. With updated credentials, the Win10 workstation was successfully joined to "widgets.domaincontroller".

How to join a domain: https://learn.microsoft.com/en-us/windows-server/identity/ad-fs/deployment/join-a-computer-to-a-domain

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/joindomain.png)
