<h1><b>Azure Virtual Machines and Networking</b></h1>


<h2>Description</h2>
This project dives into network monitoring by looking at the communication between two virtiual machines made in Azure. By filtering through network protocols in Wireshark, specific interactions are examined.
<br />


<h2>Environments and Utilities Used</h2>

- <b>Microsoft Azure</b>
- <b>Virtual Machines</b>
- <b>Remote Desktop Connection</b> 
- <b>Wireshark</b>
- <b>Various Network Protocols (ICMP, SSH, DHCP, DNS)</b>
- <b>Command-Line Tools(Windows Powershell</b>

<h2>Operating Systems Used </h2>

- <b>Windows 10</b>
- <b>Ubuntu 24.04</b>

<h2>Project Walk-through:</h2>

<h3>Create a Resource Group</h3>
<p>When creating the resource group, pay close attention to the location you are selecting. This will come in hand in the next step because you will want to have eveything in the same location. In this lab, I chose "East US."</p>
<img src="">

<h3>Make The First Virtual Machine: Windows 10 Pro</h3>
<ul>
  <li>When making the virtual machines, make sure to put them in the same resource group that was made earlier</li>
  <li>After completing the basic settings, you can skip the other settings and create the virtual machines.</li>
  <li>Most importantly, make sure that they are in the same virtual network.</li>
</ul>
<img src="Screenshot 2025-01-14 094831.png"  width="80%">

<h3>Make The Second Virtual Machine: Linux Ubuntu</h3>
<img src="Screenshot 2025-01-14 094855.png"  width="80%">

<h3>Connect to the Windows virtual machine using its public IP address with Remote Desktop</h3>
<img src="Screenshot 2025-01-14 094155.png"  width="80%">

<h3>Download Wireshark</h3>
<p>This application will be used to monitor network traffic. When downloading, there is no need to alter the settings. You can simply click "next" until the application is installed.</p>
<img src="2025-01-14 175955.png"  width="80%">

<h3>Open Wireshark and double-click on "Ethernet"</h3>
<img src="2025-01-14 180821.png"  width="80%">
