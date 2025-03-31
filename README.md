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
 <p> 
</p>

Go to Vm in Azure -> Click Dc-1 -> Public Ip Address -> Remote Desktop -> Enter Username/Password
 <p> 
</p>

![image](https://github.com/user-attachments/assets/ae460eb6-42f8-49fa-b969-a4cba01dd50d)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/3720286a-d340-48b3-822f-7c4e70563ddb)
 <p> 
</p>

2. Install Active Directory
 <p> 
</p>

Start -> Server Manager -> Add Roles and Features -> Next 3x -> Select Active Directory Domain Services -> Add Features -> Next 3x -> Check "Restart if Required" -> Yes -> Install -> Close
 <p> 
</p>

![image](https://github.com/user-attachments/assets/dc8a6b66-4b75-446f-845a-316db3f4d383)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/2b31d70c-9520-4681-b6d8-b38fbf9323fc)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/0b553b39-d7bd-4814-ba32-277347f7cd37)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/137b8b17-b426-4bac-a87f-fa07cb099c49)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/b0beb1cb-fa75-4c11-b17e-beab02e19557)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/bad329b7-11be-4970-8f40-73954a47c272)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/acdc73e9-2dda-4987-adc7-f2c35334954a)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/7a9ee9ce-92cf-4e6c-9f66-994a10b5d57a)
 <p> 
</p>

3. Configure Dc-1 (actually become Domain Controller)
 <p> 
</p>

Start -> Server Manager -> Click Flag/Caution Sign -> Click "Promote This Server to a Domain controller" -> Add a New Forest -> Type Root Domain Name -> Next -> Type Password -> Next -> *Note* make sure "Create DNS delegation" is Unchecked -> Next 4x -> Install
 <p> 
</p>

![image](https://github.com/user-attachments/assets/be477151-bf63-42e7-a328-351c17b9a2c0)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/b94041cd-9f10-4ab8-ab34-59ce29fe61f2)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/5cbc91fb-4c15-4823-a578-4913d958f78b)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/20394feb-c017-44d9-b793-80892659e7bb)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/7779b3c3-ffc7-4c3a-a4cb-92ea6446f0f4)
 <p> 
</p>

Dc-1 will log out (prompt you to close) to restart 
 <p> 
</p>

4. Login back into to Dc-1
 <p> 
</p>

Go to Vm in Azure -> Click Dc-1 -> Public Ip Address -> Remote Desktop -> Enter Username: "Specify Domain Name (back slash) original Username" -> Enter password
 <p> 
</p>

![image](https://github.com/user-attachments/assets/bf0cd485-ebff-4738-885f-bf7bf3876da9)

 <p> 
</p>

![image](https://github.com/user-attachments/assets/4c5c4133-3260-461c-930f-0c056ff75a2d)
 <p> 
</p>

5. Create Two Organizational Units(folders)
 <p> 
</p>

Start -> Windows Administrative Tools -> Active Directory Users and Computers -> Rt Click Domain Name -> New Organizational Unit (Org. Unit) -> Enter (Org. Unit) Name "_ADMINS" (spelled excatly) -> Ok
 <p> 
</p>

![image](https://github.com/user-attachments/assets/d0352e96-f3f9-4294-b2d0-5db6aed1f92d)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/6d120792-0c13-4341-beeb-36fb24684f13)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/cde91f54-bbca-4e1e-b024-3138a4b71f19)
 <p> 
</p>

Create second Unit
 <p> 
</p>

Rt Click Domain Name -> New Organizational unit (Org. Unit) -> Enter (Org. Unit) Name "_EMPLOYEES" (spelled excatly) -> Ok
 <p> 
</p>

![image](https://github.com/user-attachments/assets/6d120792-0c13-4341-beeb-36fb24684f13)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/cde91f54-bbca-4e1e-b024-3138a4b71f19)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/12634c20-2d5e-454a-9fac-07be4b1bcbaa)
 <p> 
</p>

6. Create Domain Admin User
 <p> 
</p>

Click the first (Org. Unit) "_ADMINS" -> Rt Click empty space -> New -> User -> Enter Name -> Enter Login Name -> Next -> Enter Password -> Uncheck "User must change password at next login" -> Check " Password never changes" -> Next -> Finish -> Save Crendtials to Notepad
 <p> 
</p>

![image](https://github.com/user-attachments/assets/d0f47ea9-0a4c-485e-acc2-12b0a6238659)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/dd6a1e66-a1f6-44cd-8d00-530839b4eb85)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/4d395ab7-5d65-4ced-9c64-3949406ac6da)
 <p> 
</p>

7. Make account an Admin Account (Join to domain Security Group)
 <p> 
</p>

Rt Click Admin Account (just created) -> Properties -> Member of -> Under "Enter the object names to select" type "domain names" (spelled excatly) -> Check Names -> Ok -> Apply -> Ok
 <p> 
</p>

![image](https://github.com/user-attachments/assets/3bbf68f3-37b9-4eee-a612-9d7548317edc)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/f91d99a6-c385-4061-b094-3a10a2220a6d)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/a4bdfe90-9d0d-469b-8169-407ee86934ef)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/6dd72024-faca-4f11-8ddb-10a0d83a2388)
 <p> 
</p>

8. Log out of DC-1 (Domain Controller) / Login back into to Dc-1 as Admin User (just created)
 <p> 
</p>

Remote desktop -> Public Ip Address -> Enter Username: "Specify Domain Name (back slash) Domain Admin Username" -> Enter Domain Admin Password
 <p> 
</p>

![image](https://github.com/user-attachments/assets/48004991-ca3d-4e0d-a335-1e9f9ae025af)
 <p> 
</p>

Now we will join the Second Virtual Machine (Client-1) to the Domain
 <p> 
</p>

9. Login to Client-1
 <p> 
</p>

Go to Vm in Azure -> Client-1 -> Public Ip Address -> Remote Desktop -> Enter Username/Password
 <p> 
</p>

![image](https://github.com/user-attachments/assets/ae460eb6-42f8-49fa-b969-a4cba01dd50d)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/beb3e8be-a006-45ac-9223-3c87f4e6aa58)
 <p> 
</p>

Rt Start -> System -> Rename Pc Advanced -> Computer Name -> Change -> Select Domain -> Enter Name of the Domain -> Ok -> Enter Admin Username/Password -> Ok -> Ok -> Restart/Login
 <p> 
</p>

![image](https://github.com/user-attachments/assets/09fad2df-d8c6-4df3-9802-72c4ef54c325)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/556fe0d6-8b49-4a1c-800c-ce97762c43e7)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/70cd08ae-9bf0-461c-9f9e-fee95ed06f80)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/e37e17cb-ef8f-428a-af07-ddccd1ee87dc)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/8604d45e-c889-4eb3-880c-90787c1cff17)
 <p> 
</p>

10. Check if Client-1 has joined the Domain
 <p> 
</p>

Go back to Dc-1 -> Search bar -> Type "Active Directory Users and Computers" -> Open -> Expand the Domain Name -> Click Computers
 <p> 
</p>

![image](https://github.com/user-attachments/assets/6b12a705-c00f-40d7-a24c-9b9e4ab7cd58)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/c94263ba-0e7b-433e-8bc1-0fbe29c6a150)
 <p> 
</p>

11. Create New Organizational Unit(folder)
 <p> 
</p>

Active Directory Users and Computers -> Rt Click Domain Name -> New Organizational Unit (Org. Unit) -> Enter (Org. Unit) Name "_ClientS" (spelled excatly) -> Ok -> Drag Client-1 from Computer (Org. Unit) to "_ClientS"
 <p> 
</p>

![image](https://github.com/user-attachments/assets/6d120792-0c13-4341-beeb-36fb24684f13)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/cde91f54-bbca-4e1e-b024-3138a4b71f19)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/bee62b4a-8aec-4415-9f0c-e89c350c7d99)
 <p> 
</p>

![image](https://github.com/user-attachments/assets/1048ccf7-6d80-4b45-b43f-836bf50e7055)
 <p> 
</p>

Congratulations on successfully configuring and deploying Active Directory. Now you are ready for the last project were you can gain experience with Powershell creating Users, using Group policy, and Managing the User Accounts. 
