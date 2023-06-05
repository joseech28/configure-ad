<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://imgur.com/JECEQVO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1. I log in to the Azure portal using my Azure account credentials, feeling excited about setting up our Domain Controller VM.
Once inside the Azure portal, I navigate to the dashboard and click on the "Create a resource" button, ready to kickstart the process.
In the Azure Marketplace, I search for "Windows Server" and carefully select the Windows Server version that suits our needs.
With a sense of anticipation, I click on the "Create" button, beginning the setup process for our Domain Controller VM 
In the Basics tab, I provide the necessary details for the VM: Subscription: I choose the appropriate subscription for our organization.
Resource group: Since it's the first time, I select "Create new" and enter a name like "DC-ResourceGroup" to create a dedicated resource group.
Virtual machine name: I give it the name "DC-1" to represent our Domain Controller VM.
</p>
<br />

<p>
<img src="https://imgur.com/1N1J4Nh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
2. After successfully setting up the Domain Controller VM, I'm excited to create a Client VM to join our domain and start testing our Active Directory setup.
I log in to the Azure portal using my Azure account credentials, ready to proceed with creating the Client VM.
Once inside the Azure portal dashboard, I navigate to the Resource Group "DC-ResourceGroup" that we previously created for our Domain Controller.
Within the Resource Group, I click on the "Add" button to begin the process of adding a new resource.
In the Azure Marketplace, I search for "Windows 10" and select the Windows 10 version that best fits our requirements.
With anticipation, I click on the "Create" button, initiating the setup process for our Client VM.
In the Basics tab, I provide the necessary details for the VM: Subscription: I choose the appropriate subscription, ensuring it aligns with our organization's Azure resources.
Resource group: I select the existing Resource Group "DC-ResourceGroup" to keep our Client VM organized within the same group as the Domain Controller.
Virtual machine name: I enter "Client-1" as the name for our Client VM.

</p>
<br />

<p>
<img src="https://imgur.com/jvsUXB9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3. In the VM's overview page, I click on the "Networking" option in the left-hand menu to manage its network settings.
Under the Networking tab, I find the NIC associated with our Domain Controller VM and click on it to access its configuration.
Within the NIC configuration page, I locate the "IP configurations" section and select the existing IP configuration for our Domain Controller.
In the IP configuration settings, I look for the "Private IP address" option and choose to set it as static instead of dynamic.
</p>
<br />



<p>
<img src="https://imgur.com/t4yYfQa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
4. After a brief moment, the Remote Desktop client logs me in to "Client-1", and I am now inside the VM's desktop environment.
With "Client-1" now at my disposal, I open the command prompt by clicking on the Start menu, typing "cmd," and selecting the Command Prompt application.
The command prompt window appears, ready for me to enter commands and perform various tasks.
To initiate a perpetual ping to the private IP address of our Domain Controller VM, "DC-1", I type the following command: ping -t <DC-1's private IP address>.
Excitement builds as I press the Enter key, and the perpetual ping command starts sending ICMP echo requests to the private IP address of "DC-1".
I observe the command prompt as it continuously displays the round-trip time and status of each ping request sent to "DC-1".
<br />
  
  <p>
<img src="https://imgur.com/BZ0yusB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
5. Going back to DC-1 I open the Remote Desktop application on my local machine, ready to establish a connection with our Domain Controller VM, "DC-1".
In the Remote Desktop window, I enter the IP address or hostname of "DC-1" and click on the "Connect" button, initiating the connection attempt.
The Remote Desktop client establishes a connection with "DC-1", and I am presented with the login screen for the VM.
<br />

<p>
<img src="https://imgur.com/yemaoS2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3.Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/5zyVgf5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
4Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/mMysz5R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
5Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/FYSAzeZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
6Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/or0PKT3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
6Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/6SChUqt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
6Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/aU1jgmT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
9Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/FHod5rh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
10Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/tVX4cHu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
11Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
<img src="https://imgur.com/3WeZ6G2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
13Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/IopLEnz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
14Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/p5rBfrd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
15Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/z8fybDX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
16Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/aylRgJK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
17Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/CHoKfS2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
18Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/Y7mqoQd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
19Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/jdd4MYV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
20Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/Xe5fZBJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
21Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/OHxwKbO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
22Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />



<p>
<img src="https://imgur.com/UjUhJkS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
24Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/MnzYVqj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
25Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/1WqZq6j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
26Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/Pr9FTmB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
27Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/1Mbmc0m.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
28Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/2LNT43T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
29Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/4FxqyfE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
30Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/IRNEhO1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
31Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/fqH7Kyq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
32Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />



<p>
<img src="https://imgur.com/nh7NjC1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
34Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/vqM71p5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
35Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://imgur.com/dXa0VCQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
36Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


