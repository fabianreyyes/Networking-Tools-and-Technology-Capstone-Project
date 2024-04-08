## Stage 4- LAMP Setup

In this stage we added a Ubuntu server and connected it to our DMZ-SWITCH to serve as our Linux, Apache, MySQL, Php server.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/endingtopologys4.png)

# Prepare Ubuntu Server

Upon logging in with default credentials, we encountered an issue where the LAMP server lacked network connectivity due to the inability to lease a DHCP address. Given the absence of a DHCP server for the DMZ network, we proceeded to assign a static address and set specific DNS servers. 

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/staticipubuntu.png)

Switching to root in the terminal, we edited the host files by appending "localhost.localdomain localhost" and "www.widgets.localdomain www" to the /etc/hosts file. Subsequently, we utilized hostnamectl to set the hostname to "www." Upon completion of these tasks, we initiated a comprehensive update and upgrade of all server packages to ensure system currency and integrity.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/etchostfiles.png)

# Install DokuWiki

In our lab environment, we initiate the installation process by accessing the Terminal and elevating privileges to root. We proceed with the installation of DokuWiki, a popular open-source wiki platform. This involves installing necessary PHP dependencies, enabling the Apache web server, and configuring firewall rules to allow Apache traffic. We also downloaded the DokuWiki package and extract it to the appropriate directory within the web server's root.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/LAMProot.png)

Next, we create the configuration file for DokuWiki, specifying server settings and access permissions within the Apache virtual host configuration. After saving and exiting the configuration editor, we finalize the setup by copying essential files, adjusting ownership permissions, and validating the Apache configuration.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/configfilewiki.png)

To ensure successful access to the DokuWiki installer, we perform verification steps, including creating a DNS record on our Domain Controller (DC) and configuring DNS Manager accordingly. Once the DNS record is established, we proceed to access the DokuWiki installer URL from a Windows 10 workstation's web browser. This step-by-step process ensures a smooth installation and setup of DokuWiki for collaborative documentation and knowledge management within our lab environment.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/Win10Wiki.png)

# Configure DokuWiki

Accessed the DokuWiki installer URL from Win10 and provided installation details such as wiki name, superuser credentials, and ACL policy. Back on the LAMP server we renamed the install.php file on the server to prevent unauthorized access or accidental deletion. Accessed the Wiki URL back on Win10 and logged in with the superuser credentials. Created the start page for the wiki to document network resources. Added network resource details including firewall, Win10, DC, IIS, and WWW servers, along with their hostnames, FQDNs, network information, and services. Reviewed the notes added to the wiki, identifying the need to create (A) records for firewall and IIS servers on the DC. Created host (A) records for firewall.widgets.localdomain and iis.widgets.localdomain on the DC, ensuring to uncheck create PTR record. Updated the notes on the wiki with the creation status of the A records for firewall and IIS servers.

# VIP Setup

Accessed the firewall GUI from Win10. Created a Virtual IP (VIP) on the WAN interface, mapping external port 80 to internal port 80 and LAMP Server IP address. Modified the WAN-to-DMZ firewall policy to use the newly created VIP as the destination. Identified the WAN IP address of the firewall, noting that it's dynamic and may change. Accessed the wiki from a web browser on a home computer using the WAN IP address of the firewall.
