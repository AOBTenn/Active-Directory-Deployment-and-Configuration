# Active-Directory-Deployment-and-Configuration

Active-Directory-Configuration-and-Deployment-of-Active-Directory

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Active Directory

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Windows Server 2022 Azure Edition


<h2>Deployment Steps</h2>

1. Login to Domain Controller (Dc-1)

Go to Vm in Azure -> click Dc-1 -> Public ip address -> Remote desktop -> Enter Username/password

3. Install Active Directory

Start -> Server Manager -> add roles and Features -> Next 3x -> select active Directory Domain services -> Add Features -> Next 3x -> check "Restart if Required" -> yes -> Install -> Close

5. Configure Dc-1 (actually become Domain controller)

Start -> Server Manager -> click flag/caution sign -> click "Promote This Server to a Domain controller" -> add a new forest -> Type Root domain name -> Next -> type Password -> Next -> *Note* make sure "Create DNS delegation" is Unchecked -> Next 4x -> Install

Dc-1 will log out (prompt you to close) to restart 

4. Login back into to Dc-1

Go to Vm in Azure -> click Dc-1 -> Public ip address -> Remote desktop -> Enter Username: "Specify Domain name (back slash) original username" -> Enter password

6. Create Two Organizational Units(folders)

Start -> windows Administrative tools -> Active directory Users and computers -> Rt click domain name -> New Organizational unit (Org. Unit) -> Enter (Org. Unit) name "_ADMINS" (spelled excatly) -> Ok

Create second Unit
Rt click domain name -> New Organizational unit (Org. Unit) -> Enter (Org. Unit) name "_EMPLOYEES" (spelled excatly) -> Ok

8. Create Domain admin User

Click the first (Org. Unit) "_ADMINS" -> Rt click empty Space -> New -> User -> Enter Name -> Enter login name -> Next -> Enter Password -> Uncheck "User must change password at next login" -> check " Password never changes
-> next -> Finish -> Save creentials to Notepad

10. Make account an Admin Account (Join to   domain Security Group)

Rt click admin acc. (just created) -> properties -> Member of -> Under "enter the object names to select" type "domain names" (spelled excatly) -> check names -> Ok -> apply -> Ok

12. Log out of DC-1 (domain) controller / Login back into to Dc-1 as Admin User (just created)

Remote desktop -> Public ip address -> Enter Username: "Specify Domain name (back slash) Domain admin username" -> Enter Domain admin password

 Now we will join the Second Virtual Machine (Client-1) to the Domain

9. Login to Client-1

Go to Vm in Azure -> click Client-1 -> Public ip address -> Remote desktop -> Enter Username/password

Rt Start -> System -> Rename Pc Advanced -> Computer Name -> Change -> select Domain -> Enter name of the domain -> Ok -> Enter Admin Username/Password -> Ok -> Ok -> Restart / login

11. Check if Client-1 has joined the domain

Go back to Dc-1 -> Search bar -> type "Active directory Users and computers" -> open -> Expand the domain name -> click computers

13. Create New Organizational Unit(folder)

Active directory Users and computers -> Rt click domain name -> New Organizational unit (Org. Unit) -> Enter (Org. Unit) name "_ClientS" (spelled excatly) -> Ok -> Drag Client-1 from Computer (Org. Unit) to "_ClientS"

Congratulations on Successfully Configuring and deployed Active directory. Now you are ready for the last project were you can gain experience with powershell creating users, using group policy, and managing the user accpounts. 
