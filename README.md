# Active-Directory-Deployment-and-Configuration

![image](https://github.com/user-attachments/assets/e2d78ecf-468d-4d2b-8fc4-d839bf116ed9)

<h2>Description </h2>

In this second project we are going to actually install and configure Active Directory.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Active Directory

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Windows Server 2022 Azure Edition


<h2>Deployment Steps</h2>

1. Login to Domain Controller (Dc-1)

Go to Vm in Azure -> click Dc-1 -> Public Ip Address -> Remote desktop -> Enter Username/Password

3. Install Active Directory

Start -> Server Manager -> Add Roles and Features -> Next 3x -> Select Active Directory Domain Services -> Add Features -> Next 3x -> Check "Restart if Required" -> Yes -> Install -> Close

5. Configure Dc-1 (actually become Domain controller)

Start -> Server Manager -> Click flag/caution sign -> Click "Promote This Server to a Domain controller" -> Add a New Forest -> Type Root Domain Name -> Next -> Type Password -> Next -> *Note* make sure "Create DNS delegation" is Unchecked -> Next 4x -> Install

Dc-1 will log out (prompt you to close) to restart 

4. Login back into to Dc-1

Go to Vm in Azure -> click Dc-1 -> Public ip address -> Remote desktop -> Enter Username: "Specify Domain Name (back slash) original Username" -> Enter password

6. Create Two Organizational Units(folders)

Start -> Windows Administrative Tools -> Active directory Users and Computers -> Rt Click Domain Name -> New Organizational Unit (Org. Unit) -> Enter (Org. Unit) Name "_ADMINS" (spelled excatly) -> Ok

Create second Unit
Rt Click Domain Name -> New Organizational unit (Org. Unit) -> Enter (Org. Unit) Name "_EMPLOYEES" (spelled excatly) -> Ok

8. Create Domain Admin User

Click the first (Org. Unit) "_ADMINS" -> Rt Click empty space -> New -> User -> Enter Name -> Enter Login Name -> Next -> Enter Password -> Uncheck "User must change password at next login" -> Check " Password never changes"
-> next -> Finish -> Save Crendtials to Notepad

10. Make account an Admin Account (Join to domain Security Group)

Rt Click Admin Account (just created) -> Properties -> Member of -> Under "enter the object names to select" type "domain names" (spelled excatly) -> Check Names -> Ok -> Apply -> Ok

12. Log out of DC-1 (domain) controller / Login back into to Dc-1 as Admin User (just created)

Remote desktop -> Public Ip Address -> Enter Username: "Specify Domain Name (back slash) Domain Admin Username" -> Enter Domain Admin Password

 Now we will join the Second Virtual Machine (Client-1) to the Domain

9. Login to Client-1

Go to Vm in Azure -> Click Client-1 -> Public Ip Address -> Remote Desktop -> Enter Username/Password

Rt Start -> System -> Rename Pc Advanced -> Computer Name -> Change -> Select Domain -> Enter Name of the Domain -> Ok -> Enter Admin Username/Password -> Ok -> Ok -> Restart/Login

11. Check if Client-1 has joined the Domain

Go back to Dc-1 -> Search bar -> Type "Active directory Users and Computers" -> Open -> Expand the Domain Name -> Click Computers

13. Create New Organizational Unit(folder)

Active Directory Users and Computers -> Rt Click Domain Name -> New Organizational Unit (Org. Unit) -> Enter (Org. Unit) Name "_ClientS" (spelled excatly) -> Ok -> Drag Client-1 from Computer (Org. Unit) to "_ClientS"

Congratulations on Successfully Configuring and deployed Active directory. Now you are ready for the last project were you can gain experience with powershell creating users, using group policy, and managing the user accpounts. 
