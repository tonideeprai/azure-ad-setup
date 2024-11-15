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
- Command Line Interface

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

- Creating  3 organization units in Active Directory Users and Computers (ADUC)
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
  <p><img width="90%" alt="Screenshot 2024-11-11 at 3 56 00 PM" src="https://github.com/user-attachments/assets/9e295404-284d-4218-8fa4-5f94e0e6238f"   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 3 56 46 PM" src="https://github.com/user-attachments/assets/3b1f4e87-fcaf-42cc-9390-a0f963b33c18">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 3 57 19 PM" src="https://github.com/user-attachments/assets/b0ebff9e-3519-4495-99f2-a3b791e68a21">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 5 10 28 PM" src="https://github.com/user-attachments/assets/45f6a069-e268-4c9c-be48-1e4b7c7fed6a">
   </p>

- Adding janed_admin to the “Domain Admins” Security Group
    <p><img width="90%" alt="Screenshot 2024-11-11 at 5 12 50 PM" src="https://github.com/user-attachments/assets/2300090e-af9f-46f7-85a0-45882a731655">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 5 13 27 PM" src="https://github.com/user-attachments/assets/bbf6041f-245c-45d8-a66e-f618cfa8dced">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 5 15 56 PM" src="https://github.com/user-attachments/assets/1f1507d0-f38b-4848-80d7-3c6532b95e31">
   </p>
<hr>
<h3>Joining a client to the domain</h3>

- Joining client-1 to the domain (mydomain.com)
  <p><img width="90%" alt="Screenshot 2024-11-11 at 5 42 26 PM" src="https://github.com/user-attachments/assets/4896d251-6132-4134-8592-5dcb03c993dd">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 5 43 13 PM" src="https://github.com/user-attachments/assets/0ced3bba-b91b-47e9-bd9c-413a2ddabab7">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 5 44 41 PM" src="https://github.com/user-attachments/assets/e6e54a5f-0e9b-4cf9-b7dd-0acaf36514fe">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 5 46 56 PM" src="https://github.com/user-attachments/assets/b29a4db0-ee40-46f8-8b99-0fce9ae46fde">
   </p>
   <p><img width="90%" alt="Screenshot 2024-11-11 at 5 47 37 PM" src="https://github.com/user-attachments/assets/a86c8d2a-a754-4cc5-ad08-50b39cb496a6">
   </p>
- Moving client-1 to _CLIENTS OU in ADUC
  <p><img width="90%" alt="Screenshot 2024-11-11 at 5 54 56 PM" src="https://github.com/user-attachments/assets/fbd28a5e-ee2f-4ee7-bd71-deaba0dbed2f">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 5 56 11 PM" src="https://github.com/user-attachments/assets/73bbf25a-0a65-4360-8855-d28bb2fa6678">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-11 at 5 57 03 PM" src="https://github.com/user-attachments/assets/8f53344b-5dff-40ce-88c0-0dcfe721ddd7">
   </p>
   <hr>
<h3>Setting up Remote Desktop for non-admin users</h3>

- Allowing “domain users” access to remote desktop in System > Remote Desktop (client-1)
  <p><img width="90%" alt="Screenshot 2024-11-13 at 9 17 14 AM" src="https://github.com/user-attachments/assets/f33b6d1c-a264-42cc-89ed-18dce3de5097">
   </p>
- Non-admin users can now log into client-1
  <p><img width="1511" alt="Screenshot 2024-11-13 at 9 18 27 AM" src="https://github.com/user-attachments/assets/94cf5bdc-dff2-4c95-ba66-35197b9912b5">
   </p>
<hr>
<h3>Generating users</h3>

- Creating .ps1 file in dc-1 machine with the  <a href="https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1">script</a> to generate users in PowerShell ISE ( as an administrator)
  <p><img width="90%" alt="Screenshot 2024-11-14 at 1 30 09 PM" src="https://github.com/user-attachments/assets/9722adc5-f880-477b-90c1-aedf7e089747">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-14 at 1 36 12 PM" src="https://github.com/user-attachments/assets/ab79a86a-27d7-4d20-8868-d0d74a337b59">
   </p>
- Checking the newly generated users in ADUC
  <p><img width="90%" alt="Screenshot 2024-11-14 at 1 37 55 PM" src="https://github.com/user-attachments/assets/b5f8a1f3-328b-41af-ad89-0add1d9d7e7c">
   </p>
- Attemping to login with a user account
  <p><img width="90%" alt="Screenshot 2024-11-14 at 1 42 29 PM" src="https://github.com/user-attachments/assets/56d8a7a6-50b0-4f64-ba0f-cc2c4f50ca19">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-14 at 1 45 10 PM" src="https://github.com/user-attachments/assets/4c26ec9a-2efc-4e6a-b744-9ea6a5c05303">
</p>

- Checking the username
   <p><img width="90%" alt="Screenshot 2024-11-14 at 1 46 35 PM" src="https://github.com/user-attachments/assets/3188a8ff-cb47-47e8-ba85-686f99ff8d02">
</p>
<hr>
<h3>Configuring Group Policy</h3>

- Editing Account Lockout Policy in Group Policy Management Editor (dc-1)
  <p><img width="90%" alt="Screenshot 2024-11-14 at 5 44 01 PM" src="https://github.com/user-attachments/assets/aa4c646c-a64e-4550-933d-5859c83a5b82">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-14 at 5 45 54 PM" src="https://github.com/user-attachments/assets/92062101-1e95-4597-afd8-f60a71ae0d6c">
   </p>
  <p><img width="90%" alt="Screenshot 2024-11-14 at 5 47 50 PM" src="https://github.com/user-attachments/assets/bedf88c3-1c12-470d-8b55-f615f2c17214">
   </p>

- Updating the new policy
  <p><img width="90%" alt="Screenshot 2024-11-14 at 5 51 00 PM" src="https://github.com/user-attachments/assets/8d7e25d1-a833-4791-811a-93d66934e62d">
</p>
