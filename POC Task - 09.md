## Set Up a Virtual Machine in the Cloud  

### Introduction and Overview  
Setting up a virtual machine (VM) in AWS allows you to run applications, test environments, or host services in the cloud. AWS provides Amazon EC2 (Elastic Compute Cloud) instances, which function as virtual machines. After launching an EC2 instance, users can remotely connect to it using SSH (Secure Shell) to manage the server, deploy applications, and monitor the system. This document outlines the process of setting up a virtual machine in AWS, launching it, and accessing it through SSH.  

### Objectives  
- Create and launch a virtual machine (EC2 instance) in AWS.  
- Configure the instance with necessary settings and security measures.  
- Establish SSH connectivity to the EC2 instance for remote management.  

### Importance  
- **Remote Management**: SSH access enables users to manage their virtual machines remotely, ensuring flexibility in administration and troubleshooting.  
- **Scalability**: AWS allows you to launch and scale virtual machines based on your needs, enabling businesses to adapt quickly.  
- **Security**: By configuring secure SSH access, you ensure that only authorized users can connect to your virtual machine.  
- **Cost Efficiency**: AWS EC2 allows you to choose the instance type that best suits your workload, providing cost-effective solutions for running virtual machines in the cloud.  

### Steps to Set Up a Virtual Machine in AWS  

#### Step 1: Launch an EC2 Instance  
1. Log in to the **AWS Management Console** and navigate to the **EC2 Dashboard**.  

![Screenshot 2025-02-04 210956](https://github.com/user-attachments/assets/40d47d2b-f602-4c0f-94f3-4833493df73c)
2. Click **Launch Instance** to start the process of creating a new EC2 instance.  

![Screenshot 2025-02-04 211016](https://github.com/user-attachments/assets/9e8bfeda-efd8-4325-8237-2ab3f52bdebe)
3. Select an **Amazon Machine Image (AMI)** for your VM. Choose an OS like **Ubuntu, Amazon Linux, or Windows** based on your requirements.  
4. Choose an **Instance Type** (e.g., `t2.micro` for a small VM, eligible for free-tier).  
5. Configure **Storage**: Modify the storage size if needed (e.g., add an **EBS volume** if necessary).  
6. Configure **Security Group**: Set up a security group to allow SSH (`port 22`) access to the instance.  
   - Select **Create a new security group** and ensure that SSH is allowed **only from your IP address**.  
7. Review your configurations and click **Launch**.  
8. When prompted, select **Create a new key pair**, download it (`.pem` file), and store it safely (this will be used to access your VM via SSH).  

 ![Screenshot 2025-02-04 211247](https://github.com/user-attachments/assets/c9d88c1d-1e52-4092-91a3-072bbaa7c3a4)
#### Step 2: Access the EC2 Instance via SSH  
1. Navigate to the directory where your `.pem` key pair file is stored (downloaded during instance setup).  
2. Open a **terminal (Linux/macOS)** or use **PuTTY (Windows)**.  
3. Use SSH to connect to your EC2 instance using its **Public IP Address**. The command format is:  
   ```sh
   ssh -i <your-key-file.pem> ec2-user@<your-ec2-public-ip>
   ```  
   - For **Ubuntu** instances, replace `ec2-user` with `ubuntu`:  
     ```sh
     ssh -i <your-key-file.pem> ubuntu@<your-ec2-public-ip>
     ```  
4. Accept the SSH fingerprint if prompted, and you should be logged into your EC2 instance.  

![Screenshot_2025-02-04_23-09-41](https://github.com/user-attachments/assets/8d5dfd6d-081a-45e9-a53a-4e5b9f8c7999)
#### Step 3: Verify Connection and System Access  
1. Once logged in, run the following commands to check the system's status and performance:  
   ```sh
   top       # Displays system resource usage
   df -h     # Shows disk space usage
   uptime    # Displays system uptime
   ```  
2. You can now install software, configure settings, and manage the instance remotely.  

### Expected Outcome  
After following these steps, you should achieve the following:  
- A successfully launched and running EC2 instance in AWS.  
- Secure SSH access to the instance from your local machine.  
- Ability to execute commands and manage the instance remotely.  
- A working environment where you can install and configure applications as needed.  


### Conclusion  
Setting up an EC2 instance and accessing it via SSH is a fundamental skill in cloud computing. This guide provides a step-by-step approach to launching a virtual machine, securing it, and managing it effectively. By following these steps, you can leverage AWS EC2 to deploy and manage cloud-based applications efficiently.  

