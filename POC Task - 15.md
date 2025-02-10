## Use Cloud CLI Tools: Install the CLI for your cloud provider (e.g., AWS CLI). Use it to list resources, upload files to storage, and manage VMs.

### Introduction and Overview
This document outlines the process of installing and using the AWS Command Line Interface (CLI) to manage cloud resources efficiently. The AWS CLI allows users to interact with AWS services through terminal commands, providing a powerful way to automate tasks, list resources, upload files, and manage virtual machines (VMs).

### Objectives
- **To install the AWS CLI on a local machine.**
- **To configure the AWS CLI for secure access to AWS services.**
- **To list various AWS resources using CLI commands.**
- **To upload files to Amazon S3 buckets.**
- **To manage AWS EC2 instances through the CLI.**

### Importance
- **Automation Efficiency:** Streamlines cloud resource management through automation.
- **Faster Operations:** Reduces the time required for repetitive tasks compared to using the AWS Console.
- **Script Integration:** Enables easy integration into deployment scripts for CI/CD pipelines.
- **Enhanced Cloud Proficiency:** Strengthens skills in AWS services management from the command line.

### Steps

#### STEP 1: Install the AWS CLI
- **For Windows:**
  - Download the installer from the AWS CLI official page.
  - Run the installer and follow the on-screen instructions.\

![Screenshot 2025-02-10 094408](https://github.com/user-attachments/assets/e2d039c5-fb51-4a6a-80f0-3d01f230759e)
![Screenshot 2025-02-10 094422](https://github.com/user-attachments/assets/6f3479c7-fe7e-45d0-97be-5e1827857f42)


#### STEP 2: Verify the Installation
```bash
aws --version
```

![Screenshot 2025-02-10 094454](https://github.com/user-attachments/assets/e5c3f62e-bf64-4d5d-a090-988909c9cd42)

Output should display the AWS CLI version installed.

#### STEP 3: Create an Access Key for AWS CLI
- Sign in to the AWS Management Console.
- Go to the **Security credentials** tab.
- Under **Access keys**, click **Create access key**.
- Select **Command Line Interface** as Use case.
- Download the `.csv` file containing your **Access Key ID** and **Secret Access Key**.
  
![Screenshot 2025-02-10 094927](https://github.com/user-attachments/assets/1482a243-f813-4b93-95f4-b28d28fe4df4)
![Screenshot 2025-02-10 100108](https://github.com/user-attachments/assets/442f63d4-a3ea-4d1e-a6ae-33eaad0db0e8)

#### STEP 4: Configure the AWS CLI
```bash
aws configure
```
![Screenshot 2025-02-10 095148](https://github.com/user-attachments/assets/1e4b64a5-4fa2-43d5-931e-f18582c4fb18)

Provide the following details when prompted:
- **AWS Access Key ID**
- **AWS Secret Access Key**
- **Default region name** (e.g., `us-east-1`)
- **Default output format** (e.g., `json`)

#### STEP 5: List AWS Resources
- **List all S3 buckets:**
```bash
aws ec2 create-vpc
```

### Outcomes
- Successfully installed and configured the AWS CLI.
- Gained hands-on experience in listing AWS resources through CLI commands.
- Learned how to upload files to Amazon S3 using CLI.
- Developed an understanding of managing EC2 instances from the command line.
- Strengthened cloud automation skills, improving overall cloud proficiency.
