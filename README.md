# Active-Directory-Deployment-and-Configuration

Active-Directory-Configuration-and-Deployment-of-Active-Directory

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

<h2>Installation Steps</h2>

1. Login to Domain Controller (Dc-1)
   Go to Vm in Azure -> click Dc-1 -> Public ip address -> Remote desktop -> Enter Username/password

2. Install Active Directory
   Start -> Server Manager -> add roles and Features -> Next 3x -> select active Directory Domain services -> Add Features -> Next 3x -> check "Restart if Required" -> yes -> Install -> Close

3. Configure Dc-1 (actually become Domain controller)
   Start -> Server Manager -> click flag/caution sign -> click "Promote This Server to a Domain controller" -> add a new forest -> Type Root domain name -> Next -> type Password -> Next -> *Note* make sure "Create DNS delegation" is Unchecked -> Next 4x -> Install

Dc-1 will log out (prompt you to close) to restart 

4. Login back into to Dc-1
   Go to Vm in Azure -> click Dc-1 -> Public ip address -> Remote desktop -> Enter Username: "Specify Domain name (back slash) original username" -> Enter password

5. Create Two Organizational Units(folders)
   Start -> windows Administrative tools -> Active directory Users and computer -> Rt click domain name -> New Organizational unit (Org. Unit) -> Enter (Org. Unit) name (_ADMINS) -> Ok
   Create second Unit
   Rt click domain name -> New Organizational unit (Org. Unit) -> Enter (Org. Unit) name (_EMPLOYEES) -> Ok

6. Create Domain admin User
   Click the first (Org. Unit) "_ADMINS" -> Rt click empty Space -> New -> User -> Enter Name -> Enter login name -> Next -> Enter Password -> Uncheck "User must change password at next login" -> check " Password never changes
   -> next -> Finish

7. Make account an Admin Account (Join to   domain Security Group)
  Rt click admin acc. (just created) -> properties -> Member of ->
