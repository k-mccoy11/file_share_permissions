
<p align="center">

</p>

<h1 align="center">File Share Permissions Lab in Azure</h1>
<p> This tutorial demonstrates how file share permissions and security group membership affect access control.
</p>
<br/>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure
- Command Prompt/PowerShell
- Windows Client 
- Windows Server

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Windows Server 2022 

<h2>High-Level Steps</h2>

- Create Sample File Shares with Permissions
- Test Access as a Normal User
- Configure and Test TEACHERS Security Group

<h2>Actions and Observations</h2>

<h4>Create Sample File Shares with Permissions</h4>
<p>
<ul> 
  <li>Log into Domain-Controller as the domain admin (mydomain.com\kayla_admin).</li>
<li> Log into Domain-1 as a normal user (mydomain.com\gar.visen)</li>
  <li>In Domain-Controller: Create four folders.</li>
<img src="https://github.com/user-attachments/assets/6e59691a-247f-47af-b96c-8d6a67b6aa06"/>
  <ul>
<li>N_Access→ Grant Domain Admins: Read/Write permission (normal users should be denied access).</li>
<img src="![image](https://github.com/user-attachments/assets/7102fa8d-ccb7-479a-9608-ba2285e046f6)
"/>
<li>R_Access→ Grant Domain Users: Read permission.</li>
<img src="https://github.com/user-attachments/assets/a473649d-a359-4510-8027-0039a2946412"/>
    <img src="https://github.com/user-attachments/assets/363394f0-25d5-4e8f-b4b2-5c9c4914c4a4"/>
      <img src="https://github.com/user-attachments/assets/5b8270f3-1e1b-4cfb-8716-8cabc739c3f6"/> 
<li>RW_Access→ Grant Domain Users: Read/Write permission.</li>
<img src="https://github.com/user-attachments/assets/d8e787b3-410a-472c-abe0-ba955e162d6a"/>
<li>Teachers → Will configure later: Read/Write access.</li>
<img src=""/>
</ul>
  </ul>
</p>
  <br/>

  <h4>Test Access as a Normal User</h4>
<p>
<ul>
<li> On Device-1, open the shared folder (\\Domain-Controll).</li>
<li>Attempt to access each folder:</li>
<ul>
  <li>Check which folders are accessible.</li>
  <li>Try creating/modifying files where permitted.</li> 
<img src="https://github.com/user-attachments/assets/7418dbc5-9346-4149-ba72-aef8aa9318e9"/>
  <img src="https://github.com/user-attachments/assets/300343bf-0142-48f8-bc39-d78a4c89b652"/>
</ul>
</ul>
</p>
<br/>

  <h4>Configure and Test TEACHERS Security Group</h4>
<p>
<ul>
<li>On DC-1, create a "TEACHERS" security group in Active Directory.</li>
<img src="https://github.com/user-attachments/assets/ed618fbb-d801-47e2-bff0-cf72b557374b"/>
  <img src=""/>
<li>Assign permissions to the "teachers" folder:</li>
<ul>
  <li>"TEACHERS" group → Read/Write access.</li>
  <img src=""/>
</ul>
<li>On Device-1, attempt to access "accounting" as <someuser> (it should fail).</li>
  <img src=""/>
  <li>On DC-1, add (mydomain.com\beh.sih) to the "TEACHERS" group.</li>
    <img src=""/>
<li>Log back into Device-1 as (mydomain.com\beh.sih) and try accessing "teachers" again (it should now succeed).</li>
  <img src=""/>
  </ul>
</p>
Tutorial Complete!

Have a great day!


