# Domain Setup

In this stage we added a Windows2012r2 server and connected it to our LAN-SWITCH to serve as our domain controller.

![image](

## Prepare a Win2012r2 server

Updated network adapter IP addresses, conducted ping tests to verify connectivity with remote destinations on WAN, LAN, and DNS networks. Configured and synchronized NTP (Network Time Protocol) settings. Renamed Host/Computer to DC (Domain Controller). Completed a system reboot and verified changes for functionality and accuracy.

![image](

## Install Active Directory

Deployed Active Directory services and configured the computer/domain name to "domaincontroller" (Note: Instrctions stated to name it localdomain). Executed a system reboot. Subsequently, initiated the promotion process to elevate the configuration to domain controller status. After completion, performed another system reboot to finalize the configuration changes.
