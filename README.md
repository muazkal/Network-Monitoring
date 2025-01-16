<h1><b>💻 Azure Virtual Machines and Networking</b></h1> 

<h2>📝 Description</h2> 
- This project focuses on network monitoring by analyzing communication between two virtual machines in Azure. Using Wireshark, various network protocols are filtered and examined to understand specific interactions. 

<h2>⚙️ Environments and Utilities Used</h2> 
- <b>Microsoft Azure</b> 
- <b>Virtual Machines</b> 
- <b>Remote Desktop Connection</b> 
- <b>Wireshark</b> 
- <b>Various Network Protocols (ICMP, SSH, DHCP, DNS)</b> 
- <b>Command-Line Tools (Windows PowerShell)</b> 

<h2>🖥️ Operating Systems Used</h2> 
- <b>Windows 10</b> 
- <b>Ubuntu 24.04</b>

<h2>🚀 Project Walk-through</h2> 
<h3>1️⃣ Create a Resource Group</h3>
<p>When creating the resource group, ensure that the location is consistent with subsequent resources. For this lab, "East US" was selected.</p> 
<img src=""> 

<h3>2️⃣ Create the First Virtual Machine: Windows 10 Pro</h3>
<ul> 
  <li>Assign the VM to the resource group created earlier.</li> 
  <li>After completing the basic settings, you can skip advanced options and proceed with creating the virtual machine.</li> 
  <li>Ensure the virtual machine is placed in the same virtual network as other resources.</li>
</ul>
<img src="Screenshot 2025-01-14 094831.png" width="80%"> 

<h3>3️⃣ Create the Second Virtual Machine: Linux Ubuntu</h3> 
<p>Follow the same steps as above to create the Linux virtual machine, ensuring it is in the same resource group and virtual network.</p>
<img src="Screenshot 2025-01-14 094855.png" width="80%"> 

<h3>4️⃣ Connect to the Windows Virtual Machine</h3> 
<p>Use the public IP address of the Windows VM and Remote Desktop to connect to it.</p>
<img src="Screenshot 2025-01-14 094155.png" width="80%"> 

<h3>5️⃣ Download Wireshark</h3> 
<p>Install Wireshark on the Windows VM to monitor network traffic. During installation, you can simply click "Next" without altering any settings.</p>
<img src="2025-01-14 175955.png" width="80%">

<h3>6️⃣ Open Wireshark and Begin Monitoring</h3>
<p>Open Wireshark on the Windows VM and double-click on the "Ethernet" interface to begin capturing traffic.</p> 
<img src="2025-01-14 180821.png" width="80%">

<h3>7️⃣ Ping the Linux Virtual Machine</h3> 
<ul> 
  <li>Open Windows PowerShell on the Windows VM.</li>
  <li>Filter the Wireshark capture to show ICMP traffic only.</li> 
  <li>Send continuous pings to the Linux VM using its private IP address by entering: <b>ping -t [PrivateIPAddress]</b>.</li> 
</ul> 
<img src="2025-01-14 181137.png" width="80%"> 
<img src="2025-01-14 181848.png" width="80%"> 

<h3>8️⃣ Modify Inbound Security Rules</h3>
<p>Go to Azure and add an inbound security rule to the Linux VM's network security group (NSG) to block all incoming ICMP traffic (pings).</p> 
<img src="Screenshot 2025-01-14 101410.png" width="80%">
<img src="Screenshot 2025-01-14 101454.png" width="80%"> 
<img src="Screenshot 2025-01-14 101525.png" width="80%">
<img src="Screenshot 2025-01-14 101707.png" width="80%"> 

<h3>9️⃣ Remove the Security Rule</h3> 
<p>After testing, delete the rule created in the previous step to allow the Linux VM to accept pings again.</p>
<img src="Screenshot 2025-01-14 101924.png" width="80%"> 

<h3>🔟 Monitor SSH Traffic</h3>
<ul>
  <li>In Wireshark, filter the capture to show SSH traffic only.</li> 
  <li>SSH into the Linux VM from the Windows VM by entering: <b>ssh [PrivateIPAddressOfLinuxVM]</b>.</li> 
  <li>To exit the SSH session, simply type <b>exit</b>.</li> 
</ul> 
<img src="2025-01-14 182545.png" width="80%"> 
<img src="2025-01-14 183114.png" width="80%">
