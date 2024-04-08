# Stage 3- IIS Setup

In this stage we added a Windows2012r2 server and connected it to our LAN-SWITCH to serve as our Internet Information Services server.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/endingtopologys3.png)

## Prepare a Win2012r2 server

Updated network adapter IP addresses, conducted ping tests to verify connectivity with remote destinations on WAN, LAN, and DNS networks. Configured and synchronized NTP (Network Time Protocol) settings. Renamed Host/Computer to IIS (Information Internet Services). Completed a system reboot and verified changes for functionality and accuracy. We also joined the dc.widgets.domaincontroller domain.

## Meeting with Senior Engineer

We explained that our domain was called dc.widgets.domaincontroller and weve been moving on with building the small bussiness enviroment. Senior Engineer stated that the customer wanted the domain to be called dc.widgets.localdomain. He instrcuted us to demote the domain controller and reconfigure its name to 'localdomain'.

Initially, we modified the settings of W10 and IIS, transitioning them from their domain association, 'widgets.domaincontroller', to a workgroup setting, 'WORKGROUP', in order to preempt any potential synchronization complications.

We initiated the process of demoting the domain controller and renaming it to 'localdomain'.

Subsequently, we accessed the domain controller to execute the promotion process and configuration under the 'widgets.localdomain' deployment. 

Upon completion of the domain controller adjustments, we proceeded to re-establish synchronization between Win10, IIS, and the domain controller, now designated as 'widgets.localdomain', thereby reinstating the network's operational integrity.

## Install IIS role

ISS guide: https://learn.microsoft.com/en-us/iis/install/installing-iis-85/installing-iis-85-on-windows-server-2012-r2#install-iis-85-for-the-first-time-in-the-server-manager

Installed IIS (Internet Information Services) and validated functionality by accessing http://localhost via the web browser. Configured a test webpage on IIS by creating an HTML file and saving it in the directory inetpub>wwwroot. Successfully tested the webpage on both the IIS station and the Win10 station to confirm proper functionality.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/testpageiis.png)
