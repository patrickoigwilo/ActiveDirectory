<h1>Implementing Microsoft Active Directory (On-Premises) Using Microsoft Azure Virtual Machines and Configuring Users</h1>

![image](https://github.com/patrickoigwilo/ActiveDirectory/assets/162601853/0025f726-42fe-496e-abe3-e7ac219e9729)


<h2>What is Microsoft Active Directory (AD)?</h2>
Active Directory is a software for Windows domain networks, designed, built and maintained by Microsoft. It allows for creating and centrally managing thousands of user accounts from a single location. Active Directory is a database for creating and storing information in a hierarchical structure. It is easily accessible by both admin users and non-admin users. It is an encompassing system of various directory-based identity-related services. 

A Domain Controller (DC), the server that runs the Active Directory Domain Services (AD DS), is contacted whenever a user logs into a device or accesses another device across the network. The DC authenticates users, stores user information and enforces the security policy in a directory/domain.

An AD domain is a collection of objects within an AD network. An object can be a single user or a group of users or a hardware component, such as a computer or printer.

<h2>Environments and Technologies Used:</h2>

- Microsoft Azure Cloud Environment
- 2 Virtual Machines: Windows server VM (Domain Controller) and Windows 10 VM (Client)
- Microsoft PowerShell

<h2>Walk-through for Deploying AD and Creating Users:</h2>

- I began by creating 2 virtual machines in Azure. The first VM was a Windows server VM on which I would later install and configure Active Directory, thus making it the Domain Controller. The second VM was a Windows 10 VM which I configured as a regular Windows 10 device and joined it to the DC.
- The
