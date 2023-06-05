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
<img src="https://imgur.com/fqH7Kyq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
<img src="https://imgur.com/vqM71p5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
6. In DC-1. with administrative access I open the Start menu and type "Windows Firewall" to locate the Windows Firewall settings.
I click on the "Windows Defender Firewall with Advanced Security" option to open the firewall management console.
The Windows Firewall with Advanced Security window appears, presenting me with various configuration options.
I navigate to the "Inbound Rules" section in the left-hand pane and scroll down to find the "File and Printer Sharing (Echo Request - ICMPv4-In)" rule.
I right-click on the "File and Printer Sharing (Echo Request - ICMPv4-In)" rule and select "Enable Rule" from the context menu.
</p>
<br />
 
 <p>
<img src="https://imgur.com/dXa0VCQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
7. Going back to "Client-1" The rule is now enabled, allowing the Domain Controller to respond to ICMPv4 echo requests (pings).
With the ICMPv4 rule enabled, I can ensure seamless communication and network troubleshooting by receiving and responding to ICMPv4 echo requests.
Satisfied with the firewall configuration, I close the Windows Firewall with Advanced Security window.
I proceed to perform other administrative tasks on the Domain Controller, leveraging its powerful capabilities to manage our Active Directory environment.
</p>
<br />
 
<p>
<img src="https://imgur.com/t4yYfQa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
8. As soon as I press the "Control-C" keys, I feel a sense of relief as I notice the command-line interface responding. 
The process or command I was running gracefully stops, and I regain control of the command prompt.

<br />

<p>
<img src="https://imgur.com/yemaoS2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
9.With administrative access to "DC-1", I open the Server Manager by clicking on the Start menu and selecting "Server Manager" from the available options.
The Server Manager window appears, displaying an overview of the server's management tools and information.
In the Server Manager, I navigate to the "Manage" menu and click on "Add Roles and Features" to start the installation wizard.
The Add Roles and Features Wizard opens, presenting me with the installation options and choices.
I carefully review the information provided in the Before You Begin section and proceed to the Installation Type selection.
I choose the "Role-based or feature-based installation" option and click on the "Next" button to continue.
In the Select Destination Server section, I ensure that "DC-1" is selected as the target server for the installation and click on "Next".
Next, I navigate to the Server Roles selection and expand the "Active Directory Domain Services" option.
I check the box next to "Active Directory Domain Services" to select it for installation.

<br />

<p>
<img src="https://imgur.com/5zyVgf5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
10. The Active Directory Domain Services Configuration Wizard opens, ready to guide me through the process of setting up the "mydomain.com" forest.
I choose the option to "Add a new forest" since we want to create a brand new forest.
In the Root domain name field, I enter "mydomain.com" as the name for the new forest, carefully noting it down for future reference.
I review the Forest Functional Level and Domain Functional Level options and select the appropriate levels based on our requirements and compatibility.
Next, I set the Directory Services Restore Mode (DSRM) password, ensuring it meets the security standards and is memorable for future use.
I review the summary of the configuration options, double-checking that all the settings are accurate.
Feeling confident about the setup, I click on the "Install" button to begin the process of creating the "mydomain.com" forest.

</p>
<br />

<p>
<img src="https://imgur.com/mMysz5R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
11. Once the installation finishes successfully, I receive a notification confirming that "DC-1" is now a Domain Controller for the "mydomain.com" forest.
<br />

<p>
<img src="https://imgur.com/FYSAzeZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
12. With the forest set up, I can now proceed with configuring and managing the domain, creating organizational units, user accounts, and other domain resources.
<br />


<p>
<img src="https://imgur.com/6SChUqt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
13. I open the "Active Directory Users and Computers" application from the "Start" menu on my computer.
In the Active Directory Users and Computers window, I navigate to the desired container where I want to create the OU. This could be the domain root or another existing OU.
I right-click on the container and select the "New" option from the context menu. Then, I choose "Organizational Unit" from the submenu.
A dialog box appears, prompting me to enter a name for the new OU. I carefully type "_EMPLOYEES" as the name and click "OK" to confirm.
The "_EMPLOYEES" OU now appears within the selected container in the Active Directory Users and Computers window. I can proceed to manage and organize user accounts and other objects within this newly created OU.


<p>
<img src="https://imgur.com/aU1jgmT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
14. I launch the "Active Directory Users and Computers" application from the "Start" menu on my computer.
In the Active Directory Users and Computers window, I navigate to the desired container where I want to create the new OU. This can be the domain root or an existing OU.
Once I have the desired container selected, I right-click on it to open the context menu. From the context menu, I choose the "New" option and then select "Organizational Unit".
A dialog box appears, prompting me to provide a name for the new OU. I carefully type "_ADMINS" as the name and press Enter or click "OK" to confirm.
After confirming, the "_ADMINS" OU is created within the selected container in the Active Directory Users and Computers window. I can now proceed to manage and organize user accounts or other objects within this newly created OU.
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
<img src="https://imgur.com/nh7NjC1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
34Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />





