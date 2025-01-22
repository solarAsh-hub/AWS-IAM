
# AWS S3 and IAM: Step-by-Step Guide

This guide demonstrates how to set up an AWS S3 bucket, create IAM users and groups, and assign roles with specific permissions.

---

## Step 1: Create an S3 Bucket
1. **Search for S3**: In the AWS Management Console, type `S3` in the search bar and click on **S3**.
![image](https://github.com/user-attachments/assets/ffcac8fb-c431-4258-a572-b63cffdca13d)

2. **Navigate to Buckets**: Click on **Buckets** in the S3 dashboard.
<img width="600" alt="image" src="https://github.com/user-attachments/assets/0b34b461-a0ef-4088-81f4-70ab890804c0" />

3. **Create a Bucket**:
   - Click **Create Bucket**
   
![image](https://github.com/user-attachments/assets/908d44c1-7107-426c-91dd-6d53748ae377)

   - Name your bucket and leave the default settings.

![image](https://github.com/user-attachments/assets/fcd19ebb-e936-45ba-8392-19c2f22f9888)

   - Click **Create Bucket**.
4. A confirmation message will indicate that your **bucket has been created**.

![image](https://github.com/user-attachments/assets/ec40e051-100d-4815-ba8a-bdf8a1515288)


---

## Step 2: Set Up IAM Users and Groups

### Create the First IAM User
1. **Search for IAM**: In the AWS Management Console, type `IAM` in the search bar and click on **IAM**.
   
![image](https://github.com/user-attachments/assets/4a02cab7-d315-4803-80ce-a3e36e22fcd1)

2. **Navigate to Users**: Click **Users** on the left-hand taskbar.
   
<img width="300" alt="image" src="https://github.com/user-attachments/assets/00ad1667-dff9-453b-ae6f-8a5d9629bd6c"  />

3. **Create a User**:
   - Click **Create User**.
   
![image](https://github.com/user-attachments/assets/55a74b82-d0e8-4bfa-87e0-5c87a188c168)

   - Select **I want to create an IAM user**.
   - For best practices, auto-generate a password.
   - Ensure **User must create a new password at next sign-in** is checked.
![image](https://github.com/user-attachments/assets/ec3a820b-35e5-4357-85bb-eaf22fd2e4ce)


### Create a User Group for Developers
4. **Create a Group**:

![image](https://github.com/user-attachments/assets/adb054b5-1f18-4b3a-bf9c-81f7cb3b3ce7)

   - Click **Create Group** and name the group **Developers**.
   - Assign the policy **AmazonS3FullAccess**.
   - Click **Create User Group**.

![image](https://github.com/user-attachments/assets/4fc680a0-c234-4765-a96a-7fccc964260f)

5. A message will confirm that the **Developers group has been created with the proper permissions assigned**.

<img width="900" alt="image" src="https://github.com/user-attachments/assets/e3851291-2af7-44b4-8585-0adc4a6d5c86" />




### Assign the Developer Role to the User
6. **Add User to Developers Group**:
   - Assign the developer role to the user by selecting the **Developers** group.
   - Click **Next** and verify the role has been added.
   - Click **Create User** to finish.

![image](https://github.com/user-attachments/assets/ee9b3d81-f2b3-4edd-9070-5f86b4fb4d75)

7. A message will confirm that the **user has been successfully created**.

![image](https://github.com/user-attachments/assets/5ea14420-af85-4e0f-8903-25259087d202)


---

### Create the Testers Group and User
8. **Create Another User**:
   - Click **Create User**
   
![image](https://github.com/user-attachments/assets/951d8e44-56d5-49ec-a432-c02fcbae5bcb)

![image](https://github.com/user-attachments/assets/db4f57b1-a2ca-4891-89bf-4564ed883c7d)


   - Assign this user to the **Testers group**.
     
![image](https://github.com/user-attachments/assets/a942ac56-6546-4a33-8608-43337e0bd2aa)

   - Confirm the user has been added to the **Testers group**.

![image](https://github.com/user-attachments/assets/d4e7f272-bf1f-47f3-b970-35275d17c747)

   - Click **Create User**.
9. A message will confirm that the **user has been successfully created**.

![image](https://github.com/user-attachments/assets/52ad93de-2787-424c-a9e5-ce3ef2002eff)


---

### Create the Admin Role and User
10. **Create a User for the Admin Role**:

![image](https://github.com/user-attachments/assets/31333b57-08d3-4393-9662-a31c717cf216)

    
- Create your last user and assign them to the **Admin role** 
    
![image](https://github.com/user-attachments/assets/e8f811ef-037b-43e9-b36f-b588b34c9c33)

11. A message will confirm that the **user has been created**.

![image](https://github.com/user-attachments/assets/5486e166-a380-4e96-abc2-ef706920f4eb)


---

## Step 3: Test Permissions for IAM Roles

### Log in as Developer
1. Use the **console sign-in link** provided to log in as the developer.

![image](https://github.com/user-attachments/assets/3a9da4a3-cda8-4f4c-a5b3-e2a46850fbc5)

3. The system will prompt you to change your password upon first sign-in.
4. Navigate to **S3**:
 - You will have access to the bucket because the user has the **Developer role**.
![image](https://github.com/user-attachments/assets/9e16d467-5f06-4c6d-b94b-2849c7bd2daa)


### Log in as Tester
4. Log in as the tester user (**Diana.Tejada**):

![image](https://github.com/user-attachments/assets/fa52dbd0-58b3-4afc-883f-2721199f6987)

   - This user cannot view or create buckets because no permissions were assigned.

![image](https://github.com/user-attachments/assets/ee64ea3c-b0d5-48fd-901b-a45c6b48cb3d)

   - Attempting to create a bucket will result in an **Access Denied** error.

![image](https://github.com/user-attachments/assets/9c75d53f-d87f-4f46-ab55-eceaa5e70634)


### Log in as Admin
5. Log in as the admin user (**Tariq**):

![image](https://github.com/user-attachments/assets/bb13029c-112a-4cc4-941a-d3d228390a26)

   - The admin does not have access to view the bucket because no specific policy was assigned.
     
![image](https://github.com/user-attachments/assets/ec4c7389-748c-467e-bc2d-f96f30c13022)

---

## Conclusion
This guide highlights the importance of managing IAM roles and permissions to ensure secure and effective resource management on AWS. Assign the appropriate policies to roles to grant or restrict access as needed.

---


