<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket: Post-Installation Configuration</h1>

This tutorial outlines the post-installation configuration of the open-source help desk ticketing system, osTicket. This tutorial is a continuation from [osTicket: Prerequisites and Installation](https://github.com/Tpichardo/osticket-prereq). 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machine)
- [Windows App](https://apps.apple.com/us/app/windows-app/id1295203466?mt=12) for macOS or Remote Desktop for Windows  

<h2>Create a Supreme Admin Role</h2>

In osTicket <b>Roles</b> are permissions granted to Agents per department that they have access to. In our case, our Supreme Admin will have all permissions enabled.

1. Navigate to <b>Admin Panel -> Agents</b> [tab] <b>-> Roles</b>.
2. Select <b>Add New Role</b>.
3. Name: Supreme Admin.
4. Select <b>Permissions</b>.
   - Enable all permission under the <b>Tickets</b> tab, <b>Tasks</b> tab, and <b>Knowledgebase</b> tab.
5. Select <b>Add Role</b>.
