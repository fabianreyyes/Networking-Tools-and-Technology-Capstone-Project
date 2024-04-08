# Stage 5- FTP Setup

In this stage we added a Win2012r2 server and connected it to our DMZ-SWITCH to serve as FTP Host.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/endingtopologys5.png)

## Prepare a Win2012r2 server

Renamed the computer host to "ftp" and initiated a system reboot. Configured IP addresses via the network adapter, assigning a static IP for stability. Established the domain controller (DC) IP address as the primary DNS server, with the firewall's DMZ IP designated as secondary. Synchronized NTP with the domain controller's time server, specifically dc.widget.localdomain. Successfully integrated into the widgets.localdomain network.

## Install FTP Service

FTP Setup: https://vpsie.com/knowledge-base/how-to-setup-ftp-server-users-on-windows-2012-r2/

To initialize the Web Server (IIS) and FTP Server roles, we accessed the server via an administrative account and navigate through Server Manager. We selected the desired roles and features, ensuring to include management tools where applicable. We also add FTP users through the domain via Computer Management in Server Manager. Configured global IIS settings, which included FTP authentication and authorization rules, to grant appropriate access permissions. Navigate to the designated FTP root directory and create the FTP site within IIS Manager. Configured site settings such as IP address which we pointed to the LAMP server, ensuring to specify authentication methods and user access permissions. Lastly, in IIS Manager, navigate to FTP Firewall Support to configure the data channel port range, ensuring proper firewall setup. These steps establish a robust and secure FTP server environment, ready to facilitate file transfer operations effectively.
