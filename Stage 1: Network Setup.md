# Stage 1- Network setup

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/starttopology.png)

Following the guidelines in the GNS3 Guide for adding devices to the lab workspace, key additions include a Fortinet firewall, two Ethernet switches (LAN and DMZ), and a Windows 10 workstation. The WAN-SWITCH remains connected to the WAN-CLOUD. The Fortinet firewall is strategically linked: its WAN port to the WAN-SWITCH, LAN port to the LAN-SWITCH, and DMZ port to the DMZ-SWITCH. Additionally, the Windows 10 workstation is connected to the LAN-SWITCH.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/endingtopolgys1.png)

## Configure the LAN network
The initial steps in this setup process for the FortiNet firewall in GNS3 involve starting the firewall and accessing its console interface. After starting, the firewall is set up, followed by the login screen where the default credentials are provided. Upon login, a new password is set, and the LAN interface is configured according to the client's specifications, including assigning IP addresses and enabling DHCP services. Verification steps are undertaken to ensure the correctness of the configuration.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/fortigatecl.png)


## Add a Win10 workstation 
Following the setup of the Win10 workstation in the lab environment, log in with default credentials is performed, ensuring connectivity to the LAN network. Network settings are then checked according to Microsoft guidelines, focusing on TCP/IP settings and DHCP client troubleshooting. Verification of DHCP lease from the LAN network is conducted, ensuring the Win10 workstation has obtained a valid IP address and necessary configuration parameters. To validate network connectivity, ping tests target LAN, WAN, and DNS destinations. While LAN access should be successful, WAN and DNS pings are expected to fail, indicating appropriate network segmentation and isolation.

## Connect to the firewall GUI 
After setting up the Win10 workstation, the next step involves accessing the firewall's GUI from the workstation's web browser. Logging in with the previously used credentials, adjustments are made to the firewall's system settings, including hostname and timezone, enabling NTP server service, adjusting idle logout time, and enabling auto file system check. These changes are applied via the GUI interface to ensure proper system configuration. Additionally, a firewall configuration backup is taken, adhering to best practices for configuration management. Finally, the firewall is rebooted to implement the changes effectively.

![image](https://github.com/fabianreyyes/Networking-Tools-and-Technology-Capstone-Project/blob/main/images/fortigategui.png)

## Complete Network setup
In the final step of Stage 1, a comprehensive configuration is performed on the FortiGate firewall. This lengthy process involves multiple tasks, starting with connecting to the firewall GUI from the Win10 workstation and ensuring a firewall configuration backup is taken before proceeding. Network interfaces, including WAN, LAN, GUEST, and DMZ, are configured, each with specific IP addressing and settings. DNS services are enabled and configured, followed by creating service objects for LAN and DMZ networks. Firewall rules are then established to govern traffic flow between LAN, DMZ, and WAN interfaces, ensuring appropriate access control and NAT settings. Adherence to best practices is emphasized throughout the process, including taking backups before and after configuration changes.
