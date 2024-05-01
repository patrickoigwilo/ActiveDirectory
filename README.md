<h1>Implementing Microsoft Active Directory (On-Premises) Using Microsoft Azure Virtual Machines and Configuring Users</h1>

![image](https://github.com/patrickoigwilo/ActiveDirectory/assets/162601853/0025f726-42fe-496e-abe3-e7ac219e9729)


<h2>What is Microsoft Active Directory (AD)?</h2>
Active Directory is a software for Windows domain networks, designed, built and maintained by Microsoft. It allows for creating and centrally managing thousands of user accounts from a single location. Active Directory is a database for creating and storing information in a hierarchical structure. It is easily accessible by both admin users and non-admin users. It is an encompassing system of various directory-based identity-related services. 

A Domain Controller (DC), the server that runs the Active Directory Domain Services (AD DS), is contacted whenever a user logs into a device or accesses another device across the network. The DC authenticates users, stores user information and enforces the security policy in a directory/domain.

An AD domain is a collection of objects within an AD network. An object can be a single user or a group of users or a hardware component, such as a computer or printer.

![image](https://github.com/patrickoigwilo/ActiveDirectory/assets/162601853/79d87df2-dfb8-4404-b9ca-509436f000b4)


<h2>Environments and Technologies Used:</h2>

- Microsoft Azure Cloud Environment
- 2 Virtual Machines: Windows server 2022 VM (Domain Controller) and Windows 10 Pro VM (Client)
- Remote Desktop Connection application
- Windows PowerShell ISE script for creating a group of random users on the DC

<h2>Walk-through for Deploying AD and Creating Users:</h2>

- I began by creating 2 virtual machines in Azure. The first VM was a Windows server VM on which I would later install and configure Active Directory, thus making it the Domain Controller. The second VM was a Windows 10 VM which I configured as a regular Windows 10 client device and joined it to the DC.
- A few things to note: When VMs are created, they are automatically assigned NICs or Network Interface Cards which carry their IP addresses; There are two ways in which an IP address is assigned to a host automatically, either via a DHCP server (Dynamic Host Configuration Protocol) or a DNS server (Domain Naming System server) - a DNS server converts human-readable addresses to computer-readable IP addresses; Because the DC is offering AD services, I configured its IP address from dynamic to static, meaning that its IP address won't ever change as clients try to access it for data resources; Lastly, I configured the client VM to use the DC VM as its DNS server.

![image](https://github.com/patrickoigwilo/ActiveDirectory/assets/162601853/81271f4c-4986-4efb-bd63-bf875d8854e7)

![image](https://github.com/patrickoigwilo/ActiveDirectory/assets/162601853/aa642f1f-91e5-4b4f-8699-7a4c63cb8418)

- <h4>To install Active Directory on the Windows Server VM (DC):</h4>
- I remotely connected to the Windows Server VM using the Remote Desktop Connection application, installed Active Directory Domain Services and promoted the server to Domain Controller with the forest root domain, mydomain.com.

![image](https://github.com/patrickoigwilo/ActiveDirectory/assets/162601853/51d046d7-9028-45d0-9457-14b01a71e9fb)

![image](https://github.com/patrickoigwilo/ActiveDirectory/assets/162601853/85b71e13-7395-4a50-b586-3f0e1adc954b)

- After creating the forest root domain, I restarted AD DS and created a couple of organisational units and an admin user named Jane Doe.

![image](https://github.com/patrickoigwilo/ActiveDirectory/assets/162601853/fb6aa538-c12f-46f4-8c60-807d93e78994)

- Next, I joined the Windows 10 Pro Client VM to the Domain Controller. By doing this, I can log into the Client VM with the credentials of the newly created admin user, Jane Doe.
- Within my Azure portal, I set the Client VM's DNS settings to the DC's private IP address.

![image](https://github.com/patrickoigwilo/ActiveDirectory/assets/162601853/bd55ab1b-fc7b-4d93-87d1-2d3dde106222)

- Finally, using my PowerShell script, I created a group of random users and proceeded to log into the Client VM using one of the newly created random user's credentials.

![image](https://github.com/patrickoigwilo/ActiveDirectory/assets/162601853/9d60e8cc-837c-47aa-8738-5a078ad76ee2)
