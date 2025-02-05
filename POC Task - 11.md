## Set Up IAM Roles and Permissions

### Introduction and Overview
IAM (Identity and Access Management) is a core service in AWS that allows you to manage access to AWS resources securely. With IAM, you can create and manage AWS users, groups, and roles, and assign them specific permissions. 

In this document, we will walk through the process of creating an IAM role, attaching it to an EC2 instance, and testing restricted/allowed actions to verify the permissions.
### Objectives
- Understand how to create IAM roles in AWS.
- Attach IAM roles to EC2 instances.
- Test permissions by performing allowed and denied actions on the EC2 instance.

### Importance
- **Access Control:** Helps manage and restrict access to AWS resources for enhanced security.
- **Scalability:** Allows you to manage permissions at scale for numerous instances, users, and services.
- **Auditing:** IAM roles allow you to track and monitor access, ensuring that only authorized users and instances perform specific actions.
- **Least Privilege:** By granting only the necessary permissions, you ensure your EC2 instance has only the required level of access, reducing the risk of unauthorized actions.

### Steps to Set Up IAM Roles and Permissions
#### Step 1: Create an IAM Role
1. Sign in to the AWS Management Console and navigate to the IAM service.
2. In the left sidebar, click **Roles**, then click **Create role**.

![Screenshot 2025-02-04 180008](https://github.com/user-attachments/assets/3c51f0cf-3895-4d03-858d-f87547bed441)
3. Select a trusted entity type:
   - Choose **AWS service** and select **EC2** under "Use case."

![Screenshot 2025-02-04 180109](https://github.com/user-attachments/assets/a8b32616-4f84-4e3e-9e20-c8e46256c9bd)
4. Attach permission policies:
   - For example, to allow access to S3, search for and select the **AmazonS3ReadOnlyAccess** policy.
   - You can also create custom policies if needed.

![Screenshot 2025-02-04 180148](https://github.com/user-attachments/assets/3ef70200-151d-480d-bc4c-bb6d1cfe57b4)
5. Review and create the role:
   - Name the role (e.g., **EC2S3Role**) and review the configuration.
   - Click **Create role**.

#### Step 2: Attach the IAM Role to Your EC2 Instance
1. Go to the **EC2 Dashboard** in the AWS Management Console.
2. Select the EC2 instance you want to assign the IAM role to.
3. Under **Actions**, select **Security > Modify IAM role**.

![Screenshot 2025-02-04 180638](https://github.com/user-attachments/assets/57af518f-8212-42b8-8b48-ebcb595b8645)
4. In the IAM role dropdown, select the IAM role you created earlier (e.g., **EC2S3Role**).
5. Click **Update IAM role**.

#### Step 3: Verify the IAM Role and Permissions
1. SSH into the EC2 instance using your terminal or an SSH client.
2. Attempt an allowed action (e.g., accessing an S3 bucket):
   ```sh
   aws s3 ls
   ```
   If you have granted S3 permissions, this should list the S3 buckets.

![Screenshot 2025-02-04 180826](https://github.com/user-attachments/assets/fe389844-0184-4630-81d6-2c2f7b570107)
4. Attempt a denied action (e.g., writing to S3 if the policy doesn’t allow it):
   ```sh
   aws s3 mb s3://my-new-bucket-name
   ```
   If the role does not allow bucket creation, you should receive an "Access Denied" error.

![Screenshot 2025-02-04 180755](https://github.com/user-attachments/assets/c0b3e902-6c96-4c0b-8eaa-d325ae17d11e)
### Expected Outcomes
- **Successful Execution of Allowed Actions:** The EC2 instance can list S3 buckets (or perform other permitted actions based on the assigned IAM policy).
- **Access Denied for Unauthorized Actions:** Attempts to perform actions not granted in the IAM policy should fail with an "Access Denied" error.
- **Improved Security and Compliance:** Ensuring that only required permissions are assigned, reducing potential security risks.
- **Scalability and Manageability:** IAM roles streamline permission management across multiple EC2 instances without manual credential handling.

By following this guide, you will successfully configure an IAM role for an EC2 instance, ensuring controlled and secure access to AWS resources.
