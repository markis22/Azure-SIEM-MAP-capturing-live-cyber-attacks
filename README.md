<h1>AZURE SIEM Map Capturing Live Cyber Attacks</h1>

<h2>Description</h2>

This project demonstrates how exposed cloud infrastructure attracts adversaries worldwide. I deployed a Windows VM on Microsoft Azure with all inbound ports open and the firewall disabled to intentionally simulate a vulnerable host. Using a custom script, I collected and logged failed login attempt data including source IP, username, city, country, longitude, and latitude. This data was then ingested into Azure for visualization on a global map, allowing me to track attack origins, frequency, and patterns in real time. The project highlights the scale of brute-force attempts against unsecured systems and the importance of proper cloud security practices.

<br />

## Skills You will Learn

- **Azure Cloud** – Installed and configured an Azure SIEM.
- **Virtualization Management** – Deployed and configured virtual machines using Oracle VirtualBox.
- **PowerShell Scripting** – Utilized PowerShell for administrative tasks and configuration automation.
- **Cybersecurity Lab Setup** – Built a reusable virtual environment for testing security tools and scenarios.


<h2>Languages and Utilities Used</h2>

- <b>Azure Cloud<b>
- <b>Powershell</b> 


<h2>Environments Used </h2>

- <b>Windows 11 Pro</b> 

<h2>Program walk-through:</h2>

<p align="center">
 <br />
 First, set up a new account in Azure by starting a <a href="https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account?icid=azurefreeaccount" target="_blank">free trial</a>: <br/>
 <br />
 When you have an account set up, head over to portal.azure.com and in the search bar look up virtual machines <br />
 <img src="https://i.imgur.com/S3fKsjK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 Now click create and let's set it up:  <br/>
 <img src="https://i.imgur.com/WOLAbRJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Create a new resource group and name it "Honeypotlab"  <br />
 <img src="https://i.imgur.com/lwJ7B0l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Make sure the image is Windows 11 Pro and type your username and password for the VM <br />
 (Make sure you remember it, as you will need it later): <br />
 <img src="https://i.imgur.com/Okd6Ohm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Hit "next" twice until you are in the "networking" section, and for the NIC network security group, select Advanced <br />
 Under "Configure network security group," click "Create new": <br /> 
 <img src="https://i.imgur.com/lz71v10.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 delete whatever configurations were set up by default and click on "Add an inbound rule": <br /> 
 <img src="https://i.imgur.com/4B7q6zd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Set your configurations as you see them in the screenshot below: <br /> 
 <img src="https://i.imgur.com/NlXDuzU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Then don't forget to click "Add" then "OK" <br />
 Then finall "Create + Review" and boom! Your Virtual Machine is set up! <br /> 
 <img src="https://i.imgur.com/9rnPHBK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Now let's navigate to "Log Analytics Workspaces" <br /> 
 <img src="https://i.imgur.com/ZUfHRg1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Create a new Log Analytics Workspace and set the configurations as you see in the screenshot <br />
 Then click "Review + create" <br />
 <img src="https://i.imgur.com/fiNkiLZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 Next go to "Microsoft Defender for Cloud" --> "Environment settings" --> "Azure subscription 1" <br />
 <img src="https://i.imgur.com/DqjQlgT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 Turn on the server defender plan as you see in my screen <br />
 Don't forget to save <br />
 <img src="https://i.imgur.com/euDjdyn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 Go back to your "Environment settings" and select your workstation <br />
 <img src="https://i.imgur.com/3anOosf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 Make sure your server defender is also on <br />
 Don't forget to save <br />
 <img src="https://i.imgur.com/CM23EG4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 Then go to "Data Collection" on the left and select "All Events"  <br />
 Don't forget to save <br />
 <img src="https://i.imgur.com/zAemqpj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 Now assuming that your VM is setup and ready go back to your "Log Analysis Worksapce" <br /> 
 select your workstation --> "Virtual Machine" <br />  
 <img src="https://i.imgur.com/viXR5uu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 Connect your workstation to your VM <br />  
 <img src="https://i.imgur.com/EVFCuOd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 Now go to copy your VM public IP address <br />
 <img src="https://i.imgur.com/0RSZXmw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 and paste in "Remote Desktop Connection" <br />
 <img src="https://i.imgur.com/kJ8ohPb.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 Purposefully enter a wrong username and password <br />
 <img src="https://i.imgur.com/A4XyrBX.png" height="30%" width="30%" alt="Disk Sanitization Steps"/>
 <br /> 
 <br /> 
 <br /> 
 Now log in with the correct username and password your setup for the VM in the beginning <br />
 Open "Event Viewer" <br />
 Under "Windows Logs" --> "Security" --> Look for an "Audit Failure" <br />
 You'll see the failed username and the "Failure Reason" was a "Unknown Username or Password" <br />
 <img src="https://i.imgur.com/kDuXnxF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Now, to make your VM vulnerable to attacks, you will turn off your firewall. <br />
 In Windows VM search "wf.msc" <br />
 Select "Windows Defender Firewall with Advanced Security...." <br />
 and turn off your firewall for Domain, Private and Domestic Profiles <br />
 <img src="https://i.imgur.com/vM1ATPH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
 <br />
 <br />
 <br />
 In your VM, input the file <a href="https://github.com/markis22/Azure-SIEM-MAP-capturing-live-cyber-attacks/blob/main/Security_Log_Exporter" target="_blank">Security Log Exporter</a> into the VM <br />
 <img  src="https://i.imgur.com/LHusZFG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
 <br />
 <br />
 <br />
 In your VM, Navigate to a <a href="https://ipgeolocation.io/" target="_blank">Geo Locator</a>, create an account and sign up <br />
 After signing up in the dashboard, you will be provided with an API key that you need to place in the PowerShell code I provided earlier
 <img src="https://i.imgur.com/JF9CovH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br /> 
 Back to your Host machine, in Azure, navigate to "Log Analytics query packs" and create a new one and configure it the same way you see it on screen <br />
 Click "Review + Create" when done <br />
 <img src="https://i.imgur.com/TQ9hAt0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Go back to the VM and run the PowerShell code and save the output file to "failed_rdp.log" <br />
 <img src="https://i.imgur.com/cV2zZD1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
 <br />
 <br />
 <br />
 Back to Azure, navigate to "Log Analysis Workspace", select your workspace and look up "Tables" <br />
 Select Next to "Collection Paths" and set configurations as you see them on the image below <br />
 Then in "Details" call it "GEO_Failed_rdp" <br /> 
 Then "Review + Create" <br />
 <img src="https://i.imgur.com/SmLIcD6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Then in "Log Analysis Workspace" head to "logs" and at the top right change it to "KQL mode" <br /> 
 Then write a line of code "SecurityEvent | where EventID == 4625" <br />
 This will return all the failed rdp logs <br />
 <img src="https://i.imgur.com/7hnZM5E.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Now wait about 15 minutes for the VM to sync logs properly <br />
 From there run "GEO_Failed_rdp", you should see a list a list of outputs <br />
 <img src="https://i.imgur.com/5A1tVRj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Now let's set up the workspace that will help us map out the attacks we are getting on our Honeypot <br />
 <br />
 <br />
 <br />
 In Azure, navigate to "Microsoft Defender on Cloud"<br />
 <img src="https://i.imgur.com/zwAXIG6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 On the left-hand side, you will see a list of options, go to "Workbooks" and select "New" <br />
 <img src="https://i.imgur.com/AtxnfaA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Click on "Add" and when the drop-down menu appears, select "Add query" <br />
 <img src="https://i.imgur.com/SxSJyQ2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 <br />
 So now that we want to leave the script running on the VM for a few hours until we get some adversaries trying to log into our VM <br />
 When you start to get a few failed login attempt logs, you can move on to the next step <br />
 <img src="https://i.imgur.com/121MavR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br /> 
 <br />
 For "Log analysis workspace", select the drop-down menu and select "log-analysis-workspace and write your 
 <a href="https://github.com/markis22/Azure-SIEM-MAP-capturing-live-cyber-attacks/blob/main/Workbook_KQL_code" target="_blank">Query code</a> <br />
 If you don't get many results, that's fine, you need to wait some time for the adversaries to find and attack your VM <br />  
 In the drop-down menu under "Visualization," select "Map" <br />
 <img src="https://i.imgur.com/Ag8Wybf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 <br />
 <br />
 <br />
 Copy the map settings configurations <br />
 Then click on "Apply" and "Save and Close" <br />
 <img src="https://i.imgur.com/WijTzVP.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
 <img src="https://i.imgur.com/W8K5ygm.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Don't forget to save your Workbook! <br />
 <img src="https://i.imgur.com/dpkd43V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 Now leave <a href="https://github.com/markis22/Azure-SIEM-MAP-capturing-live-cyber-attacks/blob/main/Security_Log_Exporter" target="_blank">Security Log Exporter</a> running on your VM, and at the top, you adjust it to refresh the map every "10 minutes" <br />
 Here are my results for the honeypot after leaving it for about 12hours as of 8/30/2025 <br />
<br /> 
If you did this honeypot lab with me, please share with me your findings on <a href="https://www.linkedin.com/in/mark-shenouda-908708245/" target="_blank">LinkedIn!!</a> <br />
 <img src="https://i.imgur.com/GKjEpif.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
 <br />
 <br />
 <br />
</p>

