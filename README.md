<h1>AZURE SIEM Map Capturing Live Cyber Attacks</h1>

<h2>Description</h2>


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

- <b>Windows 10</b> 
- <b>Windows Server 2019</b> 

<h2>Program walk-through:</h2>

<p align="center">
First things first, we will set up a new account in Azure by starting a free trial: <br/>
https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account?icid=azurefreeaccount <br />
<br />
Then, when you have an account set up, head over to portal.azure.com and in the search bar look up virtual machines <br />
<img src="https://i.imgur.com/S3fKsjK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now click create and let's set it up:  <br/>
<img src="https://i.imgur.com/WOLAbRJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create a new resource group and name it "Honeypotlab"  <br />
<img src="https://i.imgur.com/lwJ7B0l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Make sure the image is Windows 11 Pro and type your username and password for the VM <br />
(Make sure you remember it, as you will need it later): <br />
<img src="https://i.imgur.com/Okd6Ohm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Hit "next" twice until you are in the "networking" section, and for the NIC network security group, select Advanced <br />
Under "Configure network security group," click "Create new": <br /> 
<img src="https://i.imgur.com/lz71v10.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
delete whatever configurations were set up by default and click on "Add an inbound rule": <br /> 
<img src="https://i.imgur.com/4B7q6zd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
delete whatever configurations were set up by default and click on "Add an inbound rule": <br /> 
<img src="https://i.imgur.com/NlXDuzU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<br />
<br />

<br />
<br />

<br />
<br />

<p />
