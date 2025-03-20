<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket: Post-Installation Configuration</h1>

Congratulations! Now that you've installed osTicket, this tutorial will outline the post-installation configuration settings. <br>
<i>Note</i>: This tutorial is a continuation from [osTicket: Prerequisites and Installation](https://github.com/Tpichardo/osticket-prereq). 

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
   <br>
      <img height="80%" width="80%" alt="Screenshot 2025-03-20 at 12 45 27 PM" src="https://github.com/user-attachments/assets/88eba019-5a4f-4463-9d79-2141ae653342" />

<h2>Create a Department</h2>

In osTicket, <b>Departments</b> are teams that manage specific types of customer requests with settings that control visibility, ticket assignment, email responses, and Service Level Agreements (SLAs).

1. Navigate to <b>Admin Panel -> Agents</b> [tab] <b>-> Departments</b>.
2. Select <b>Add New Department</b>.
3. Name: SysAdmins.
4. Select <b>Create Dept</b>.

<h2>Create a Team</h2>

In osTicket, <b>Teams</b> are made of of agents pulled together from different departments to handle a specfic issue.

1. Navigate to <b> Admin Panel -> Agents</b> [tab] <b>-> Teams</b>.
2. Select <b>Add New Team</b>.
3. Name: Online Banking.
4. Select <b>Create Team</b>.

<h2>Enable Users to Create Tickets</h2>

Let's configure the user settings to enable users to create tickets without the need to have a registered account. 

1. Navigate to <b>Admin Panel -> Settings</b> [tab] <b>-> Users</b>.
2. <b>Uncheck</b> the box for <b>Require registration and login to create tickets</b>.
3. Save Changes.

