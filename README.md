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
<hr>
<h3>The Setup</h2>

I have 2 virtual machines running in the same Vnet/resource group. One is meant to be a DC server and one client.

- Windows Server 2022 (named dc-1)
   - Private IP address is set to static
   - Windows Defender Firewall disabled (for testing connectivity)
- Windows 10 pro (named client-1)
    - DNS server is set to the server's private IP address
   <p><img width="90%" alt="Screenshot 2024-11-11 at 1 02 14 PM" src="https://github.com/user-attachments/assets/6863a5ae-5529-41f2-9482-334fef0c38ab">
</p>
<hr>
<h3>Active Directory Installation</h2>

- Installing Active Directory Domain Services in Server Managewr
  <p><img width="90%" alt="Screenshot 2024-11-11 at 1 13 22 PM" src="https://github.com/user-attachments/assets/f68968aa-683a-4b1a-b147-775fb647a07e">
   </p>
   <p><img width="90%" alt="Screenshot 2024-11-11 at 1 14 29 PM" src="https://github.com/user-attachments/assets/7c440d83-30f5-4a17-8c6c-feaa8ec47855">
   </p>

- Promoting dc-1 as a domain controller (mydomain.com)
    <p></p>
