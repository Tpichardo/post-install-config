<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket: Post-Installation Configuration</h1>

Congratulations! Now that you've installed osTicket, this tutorial will outline the post-installation configuration settings. <br>
<i>Note</i>: This tutorial is a continuation from [osTicket: Prerequisites and Installation](https://github.com/Tpichardo/osticket-prereq). 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machine)
- [Windows App](https://apps.apple.com/us/app/windows-app/id1295203466?mt=12) for macOS or Remote Desktop for Windows
- osTicket  

<h2>Create a Supreme Admin Role</h2>

In osTicket, <b>Roles</b> are permissions granted to Agents that define what Agents are allowed to do, like viewing, responding, or managing tickets. In our case, our Supreme Admin will have all permissions enabled.

1. Navigate to <b>Admin Panel -> Agents</b> [tab] <b>-> Roles</b>. <i>Note</i>: Some roles will already be configured for you. Feel free to examine these Roles and view their permissions. 
2. Select <b>Add New Role</b>.
3. Name: Supreme Admin.
4. Select <b>Permissions</b>.
   - Enable all permission under the <b>Tickets</b> tab, <b>Tasks</b> tab, and <b>Knowledgebase</b> tab.
5. Select <b>Add Role</b>.
   <br>
      <img height="80%" width="80%" alt="Screenshot 2025-03-20 at 12 45 27 PM" src="https://github.com/user-attachments/assets/88eba019-5a4f-4463-9d79-2141ae653342" />

<h2>Create a Department</h2>

In osTicket, <b>Departments</b> are teams that manage specific types of customer requests with settings that control visibility, ticket assignment, email responses, and Service Level Agreements (SLAs).

1. Navigate to <b>Admin Panel -> Agents</b> [tab] <b>-> Departments</b>. Similar to Roles, some Departments will already be configured for you (Maintenance, Support). 
2. Select <b>Add New Department</b>.
3. Name: SysAdmins.
4. Select <b>Create Dept</b>.
5. Delete the <b>Maintenance</b> department, as tickets default to this department, and we will not be using it in this tutorial series.
   - Select the checkbox corresponding to the <b>Maintenance</b> Department.
   - Select <b>More</b>.
     - From the drop down menu, select <b>Delete</b>.
       <br>
       <img height="80%" width="80%" alt="Screenshot 2025-03-21 at 2 38 13 AM" src="https://github.com/user-attachments/assets/8b6e6b66-9806-4679-b1cc-7fbcf0116180" />
   - In the confirmation pop up, select <b>Yes, Do it!</b> to delete the Maintenance Department.
     <br>
     <img height="80%" width="80%" alt="Screenshot 2025-03-21 at 2 40 45 AM" src="https://github.com/user-attachments/assets/b2aebe8f-eeca-4e74-bc25-c0288790f5d2" />

<h2>Create a Team</h2>

In osTicket, <b>Teams</b> consist of Agents pulled together from different Departments to handle a specfic issue.

1. Navigate to <b> Admin Panel -> Agents</b> [tab] <b>-> Teams</b>.
2. Select <b>Add New Team</b>.
3. Name: Online Banking.
4. Select <b>Create Team</b>.

<h2>Enable Users to Create Tickets</h2>

Let's configure the user settings to enable users to create tickets without the need to have a registered account. 

1. Navigate to <b>Admin Panel -> Settings</b> [tab] <b>-> Users</b>.
2. <b>Uncheck</b> the checkbox for <b>Require registration and login to create tickets</b>.
3. Save changes.

<h2>Create Agents</h2>

In osTikcet, <b>Agents</b> are individuals who are given access to the helpdesk so that they can respond and resolve the tickets. As we create our Agent, we will need to assign them to a primary department and assign them a primary role for the tickets routed to that department. 

1. Navigate to <b>Admin Panel -> Agents</b> [tab]. <i>Note:</i> There will already be a default Agent that was created when we set up osTicket.
2. Select <b>Add New Agent</b>.
3. Fill out the <b>Add New Agent</b> Form
   - Under the <b>Account</b> Tab
     - Create a <b>Name</b>, <b>Email</b>, and <b>username</b> for the Agent. Feel free to add a fake email address as you will not need to have access to this email.
     - Select <b>Set Password</b>
        - <b>Uncheck</b> the checkbox for <b>Send the agent a password reset email</b>, since the email we used is fake.
        - Create a password. <i>Note:</i> keep track of all of the credentials you set in this tutorial, as you will need them to navigate the ticketing system as an authenticated Agent later.
        - Uncheck Require password change at next login. <i>Note:</i> For the purposes of this tutorial, we're unchecking this option for simplicity. In real-life scenarios, this option should remain checked.
        - Select <b>Set</b>.
          <br>
          <img height="80%" width="80%" alt="Screenshot 2025-03-20 at 4 43 21 PM" src="https://github.com/user-attachments/assets/41ffeab4-c5ff-46fc-b39b-837e40909b53" />
   - Navigate to the <b>Access</b> tab to assign the Agent to a Primary Department
     - From the <b>Select Department</b> dropdown menu, select <b>SysAdmins</b> to add the Agent to the SysAdmins department that we created.
     - From the <b>Select Role</b> dropdown menu, select <b>Supreme Admin</b> to assign the Supreme Admin Role to the Agent. Remember that our Supreme Admin Role has all permissions enabled, so the Agent who is assigned this Role will also have all permissions enabled.
       <br>
       <img height="80%" width="80%" alt="Screenshot 2025-03-20 at 4 57 43 PM" src="https://github.com/user-attachments/assets/a5a04b82-bd4b-4459-821a-5969aba976a2" />
   - Navigate to the <b>Teams</b> tab
     - From the <b>Select Team</b> dropdown menu, select the <b>Online Banking</b> team.
       <br>
       <img height="80%" width="80%" alt="Screenshot 2025-03-20 at 4 57 59 PM" src="https://github.com/user-attachments/assets/c43eb63d-f8e8-4c09-85b0-07c4143e05fc" />
4. Select <b>Create</b>.
5. Add an Additonal Agent (You'll have 3 in total)
   - This Agent will be part of the <b>Support</b> Department and have a <b>View Only</b> Role.
     <br>
     <img height="80%" width="80%" alt="Screenshot 2025-03-20 at 5 04 08 PM" src="https://github.com/user-attachments/assets/cfa80e05-bfb0-403a-95bb-2fe15413a4bd" />

<h2>Create a User (Customer)</h2>

In osTicket, <b>Users</b> can create tickets and view their status.

1. Navigate to <b> Agent Panel -> Users</b>.
2. Select <b>Add User</b>.
3. Fill out the <b>Create User</b> form (Name + Email). Feel free to use a fake email address, as you will not need to have access to this email. However, keep track of the email address you use as you will use it later to create tickets. 
4. Select <b>Add User</b>.
5. Select <b>User Directory</b> to view your User(s).

<h2>Configure Service Level Agreements (SLAs)</h2>

The purpose of an SLA is to set a time in which the support team is expected to respond to or resolve the ticket. We will be creating 3 SLA Plans, each with different levels of severity. 

1. Navigate to <b>Admin Panel -> Manage -> SLA</b>.
2. Select <b>Add New SLA Plan</b>.
3. Fill out the <b>Add New SLA Plan</b> form & Select <b>Add Plan</b> after each SLA Plan is complete.
   - <b>Name</b>: SLA Plan name.
   - <b>Grace Period</b>: Amount, in hours, before tickets with an SLA Plan will become overdue if not closed in the allotted time. This means that the support team is expected to close a ticket under an SLA Plan with a Grace Period of 1 hour, within 1 hour of receiving it.
   - <b>Schedule:</b> The working hours during which the SLA timer is active. This means that the support team is expected to work and respond to tickets with an SLA Plan with a 24/7 schedule at any time of the day or night, all week long.
      - Sev-A SLA Plan:
         - <b>Name</b>: Sev-A
         - <b>Grace Period</b>: 1 hour
         - <b>Schedule:</b> 24/7.
             <br>
             <img height="80%" width="80%" alt="Screenshot 2025-03-20 at 6 42 55 PM" src="https://github.com/user-attachments/assets/b0a901f6-206a-4ebd-a57d-1240c84a4ee5" />
      - Sev-B SLA Plan:
         - <b>Name:</b> Sev-B.
         - <b>Grace Period:</b> 4 hours.
         - <b>Schedule: 24/7</b>.
           <br>
           <img height="80%" width="80%" alt="Screenshot 2025-03-20 at 7 22 16 PM" src="https://github.com/user-attachments/assets/4535c974-9bef-4868-8e8e-da9fbe224a8b" />
      - Sev-C SLA Plan:
         - <b>Name:</b> Sev-C.
         - <b>Grace Period:</b> 8 hours
         - <b>Schedule:</b> Monday-Friday 8:00am-5:00pm with US Holidays.
           <br>
           <img height="80%" width="80%" alt="Screenshot 2025-03-20 at 7 22 43 PM" src="https://github.com/user-attachments/assets/f3fc9285-44c1-47ca-a3a9-e1f918bf60ae" />

<h2>Create Help Topics</h2>

In osTicket, <b>Help Topics</b> are categories that help organize the types of issues or requests users submit. This is important because it helps the Users categorize the tickets when creating them and determines which Department will handle the ticket created. 

1. Navigate to <b>Admin Panel -> Manage -> Help Topics</b>.
2. Select <b>Add New Help Topic</b>.
   - Help Topics to create:
     - Business Critical Outage | <b>Parent Topic:</b> Report a Problem
     - Personal Computer Issues | <b>Parent Topic:</b> Report a Problem
     - Equipment Request | <b>Parent Topic:</b> General Inquiry
     - Password Reset | <b>Parent Topic:</b> Report a Problem
     - Other | <b>Parent Topic:</b> General Inquiry
       <br>
       <img height="80%" width="80%" alt="Screenshot 2025-03-20 at 7 45 39 PM" src="https://github.com/user-attachments/assets/bfae319a-f5a3-422f-90e1-92267b138440" />
