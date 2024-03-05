# Configure-Active Directory



<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<!--<h2>Video Demonstration</h2>-->

<!--- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)-->

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Creating a Domain Controller VM
- Creating Client-1 WM, connect to DC Domain
- Install Active Directory on DC
- Creating Users on AD

<h2>Deployment and Configuration Steps</h2>

<p>
<h3>Phase One</h3>
  
![Configuring Active Directory Phase 1 - Imgur](https://github.com/PhillisEssel/configure-ad/assets/156061642/20a12556-8005-426c-afe8-96e1c91ff74a)

<p><a href="https://imgur.com/a/5ZE6blF">More</a></p>

</p>
<p>
Resources (Azure cloud). Domain Controller "DC-1," Set DC's NIC Private IP address= static. Client VM "Client-1,". Check Topology in Network Watcher. Login to Client-1 Remote Desktop and ping DC-1'S Private IP address (perpetual ping). Login to DC and enable ICMPV4 in the local windows Firewall then check Client-1 for ping. Login to DC-1 and install Active Directory Domain Services. Promote as a DC: Set Up forest with domain name (example: mydomain.com). Restart and then log back into DC-1 as user mydomain.com\labuser.
</p>
<br />

<p>
<h3>Phase Two</h3>
  
![Configuring Active Directory Phase 2 - Imgur](https://github.com/PhillisEssel/configure-ad/assets/156061642/1d4bcfc3-deee-490d-a35c-6eaf605e0818)

<p><a href="https://imgur.com/a/Rqrejvt">More</a></p>
  
</p>
<p>
Create Admin and Normal user acccount. Create Organizational Unit "_EMPLOYEES" Create another OU "_ADMINS" Create emyployee(ex:Jane Doe) and a username(ex:jane_admin). add user to "Domain Admins" Security Group. Log out/close Remote Desktop connection to DC-1 and log back in as "mydomain.com\jane_admin." User classified by admin account. Join Client-1 to domain. In azure portal set Client-1's DNS settings to DC's Private IP address. restart Client-1 from the Azure Portal. Login to Client-1 as local admin (labuser) and join it to the domain (computer auto-restart). 
</p>
<br />

<p>
<h3>Phase Three</h3>

![Configuring Active Directory Phase 3 - Imgur](https://github.com/PhillisEssel/configure-ad/assets/156061642/4340a86f-e2a9-4ad8-abfe-8bd1f42b41df)

<p><a href="https://imgur.com/a/6cO46ET">More</a></p>
  
</p>
<p>
Login to DC, verify Client-1 appears in Active Directory Users and Computers (ADUC) under "Computers" of the domain. Remote desktop for non-admin users/Client-1. log in as domain admin > system properties, click "remote desktop" allow "domain users" access to normal non-admin user Login. Create additional users > attempt to log into Client-1 (thousands of employees/thousands of students). Login to DC-1 as admin, open Powershell_ise as administrator, create new file /paste the script into it. Run script and observe accounts being created. open ADUC and observe accounts in OU, attempt to login as one on Client-1. 
</p>
<br />
