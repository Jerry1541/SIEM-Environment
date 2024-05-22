# SIEM-Environment

## Objective

This is a personal project to familiarize and experience developing SIEM using cloud technology of Azure portal. A VM hosted on this cloud subscription, will act as honeypot for cyber attackers. Failed RDP logs will be picked up (monitored) and logged using log analytics. This information is then presented as a map, displaying the IP addresses of attackers that have attempted to log in via remote desktop.

### Skills Learned

- Understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

Azure portal subscription:
-	Azure Microsoft Sentinel (Cloud based SIEM)
-	VM (Honeypot)
-	Third part API (IPgeolocation.io) for retrieving geolocation data
-	PowerShell script to extract metadata from Windows Event Viewer
-	Log Analytics workspace (Azure) for custom logs
-	Create workbook (Azure) to display global attack data according to location and magnitude

## Steps
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
 
## References
Josh Madakor. (2021, November 1). SIEM Tutorial for Beginners | Azure Sentinel Tutorial MAP with LIVE CYBER ATTACKS! [Video]. YouTube. https://www.youtube.com/watch?v=RoZeVbbZ0o0&ab_channel=JoshMadakor
