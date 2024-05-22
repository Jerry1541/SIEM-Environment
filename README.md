# SIEM-Environment

## Objective

This is a personal project to familiarize and experience developing SIEM using cloud technology of Azure portal. A VM hosted on this cloud subscription, will act as honeypot for cyber attackers. Failed RDP logs will be picked up (monitored) and logged using log analytics. This information is then presented as a map, displaying the IP addresses of attackers that have attempted to log in via remote desktop.

### Skills Learned

- Managed Azure based SIEM with over 5,000 RDP attacks originating from Russia, China, and Europe.
- Configured Log Analytics Workspace for ingesting custom logs efficiently from a honeypot VM.
- Set up Azure Sentinel Workbooks to visualize and analyze global RDP attack patterns.

### Tools Used

Azure portal subscription:
-	Azure Microsoft Sentinel (Cloud based SIEM)
-	VM (Honeypot)
-	Third part API (IPgeolocation.io) for retrieving geolocation data
-	PowerShell script to extract metadata from Windows Event Viewer
-	Log Analytics workspace (Azure) for custom logs
-	Create workbook (Azure) to display global attack data according to location and magnitude

## Steps

<p align="center">
    <img src="https://i.imgur.com/0a4D9fz.png" height="50%" width="50%" alt=""/> <br/>
    Data flow and system architecture <br/>
</p>

-	Set up a free subscription account on Azure portal
-	Set up virtual machine
    - Make it extremely vulnerable by removing firewalls
    - Make resource group
    - Decide user credentials for VM
-	Set up Log Analytics Workspace to ingest custom logs from virtual machine
    -	Use custom PowerShell Transform Logs to retrieve data from Windows Event Viewer and send it to API ipgeolocation.io, derive IP address and other details
    - Enable these details to be send to log repository on cloud
    - Connect log analytics to VM
    - Create custom log in LAW using sample log from VM and share sample log file path
-	Set up workbook in Microsoft Sentinel to map attacks using details from the Log
    - Connect Sentinel to LAW
    - Add query for visualizing attack data
 
## Workbooks

<p align="center">
    <img src="https://i.imgur.com/HkGDg7u.png" height="50%" width="50%" alt=""/> <br/>
    Failed RDP World Map <br/> <br/>
    <img src="https://i.imgur.com/Ja78gPj.png" height="50%" width="50%" alt=""/> <br/>
    Usernames used Tiles <br/>
</p>
 
## References
Josh Madakor. (2021, November 1). SIEM Tutorial for Beginners | Azure Sentinel Tutorial MAP with LIVE CYBER ATTACKS! [Video]. YouTube. https://www.youtube.com/watch?v=RoZeVbbZ0o0&ab_channel=JoshMadakor
