<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Configurations in Azure</h1>

This lab shows how I setup, install, and configure Active Directory and how I create a thousand of users using a piece of script.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 Pro (21H2)

<h2>The Setup</h2>

I have 2 virtual machines running in the same Vnet/resource group. One is meant to be a DC server and one client.

- Windows Server 2022 (server)
   - Private IP address is set to static
   - Windows Defender Firewall disabled (for testing connectivity)
- Windows 10 pro (client)
    - DNS server is set to the server's private IP address

