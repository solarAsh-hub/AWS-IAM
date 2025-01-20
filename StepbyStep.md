
# AWS S3 and IAM: Step-by-Step Guide

This guide demonstrates how to set up an AWS S3 bucket, create IAM users and groups, and assign roles with specific permissions.

---

## Step 1: Create an S3 Bucket
1. **Search for S3**: In the AWS Management Console, type `S3` in the search bar and click on **S3**.
2. **Navigate to Buckets**: Click on **Buckets** in the S3 dashboard.
3. **Create a Bucket**:
   - Click **Create Bucket**.
   - Name your bucket and leave the default settings.
   - Click **Create Bucket**.
4. A confirmation message will indicate that your **bucket has been created**.

---

## Step 2: Set Up IAM Users and Groups

### Create the First IAM User
1. **Search for IAM**: In the AWS Management Console, type `IAM` in the search bar and click on **IAM**.
2. **Navigate to Users**: Click **Users** on the left-hand taskbar.
3. **Create a User**:
   - Click **Create User**.
   - Select **I want to create an IAM user**.
   - For best practices, auto-generate a password.
   - Ensure **User must create a new password at next sign-in** is checked.

### Create a User Group for Developers
4. **Create a Group**:
   - Click **Create Group** and name the group **Developers**.
   - Assign the policy **AmazonS3FullAccess**.
   - Click **Create User Group**.
5. A message will confirm that the **Developers group has been created with the proper permissions assigned**.

### Assign the Developer Role to the User
6. **Add User to Developers Group**:
   - Assign the developer role to the user by selecting the **Developers** group.
   - Click **Next** and verify the role has been added.
   - Click **Create User** to finish.
7. A message will confirm that the **user has been successfully created**.

---

### Create the Testers Group and User
8. **Create Another User**:
   - Click **Create Another User**.
   - Assign this user to the **Testers group**.
   - Confirm the user has been added to the **Testers group**.
   - Click **Create User**.
9. A message will confirm that the **user has been successfully created**.

---

### Create the Admin Role and User
10. **Create a User for the Admin Role**:
    - Create your last user and assign them to the **Admin role**.
11. A message will confirm that the **user has been created**.

---

## Step 3: Test Permissions for IAM Roles

### Log in as Developer
1. Use the **console sign-in link** provided to log in as the developer.
2. The system will prompt you to change your password upon first sign-in.
3. Navigate to **S3**:
   - You will have access t

