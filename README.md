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
    <p><img width="90%" alt="Screenshot 2024-11-11 at 1 22 24 PM" src="https://github.com/user-attachments/assets/feaa4a02-900e-47d5-a44b-9cec7d025392">
   </p>
   <p><img width="90%" alt="Screenshot 2024-11-11 at 1 23 05 PM" src="https://github.com/user-attachments/assets/3c5bccd0-7a3a-4744-ac07-86f7e5d64304">
   </p>
   <p><img width="90%" alt="Screenshot 2024-11-11 at 1 30 59 PM" src="https://github.com/user-attachments/assets/8f470789-bca4-400f-8eb4-811c5b83f31f">
   </p>
   <p><img width="90%" alt="Screenshot 2024-11-11 at 3 24 02 PM" src="https://github.com/user-attachments/assets/073294b8-2a09-4732-a3b0-69348d34b962">
</p>

- Logging as a domain user
  <p><img width="90%" alt="Screenshot 2024-11-11 at 3 32 02 PM" src="https://github.com/user-attachments/assets/93eb4619-e2ca-43c6-98bb-d9c0a1c94827">
</p>
<hr>
<h3>Creating Organizational Units (OU)</h3>

- creating  3 organization units in Active Directory Users and Computers (ADUC)
  - _EMPLOYEES
  - _ADMINS
  - _CLIENTS
  <p><img width="90%" alt="Screenshot 2024-11-11 at 3 45 31 PM" src="https://github.com/user-attachments/assets/c2f7ec47-85c3-4d2f-b489-54cb18b8b6c8">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 3 47 22 PM" src="https://github.com/user-attachments/assets/11108efb-56e0-439c-887b-5d96f41d0c8e">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 3 48 52 PM" src="https://github.com/user-attachments/assets/65fcfb6d-1e23-4fcc-84f7-21ca73fb1a9a">
   </p>
   <hr>
<h3>Creating a Domain Admin user</h3>

- Creating Jane Doe's user as Domain Admin under _ADMINS OU
  <p></p>
  
