## Host a Static Website on a Cloud VM: Install Apache/Nginx on your cloud VM and host a simple HTML website.  

### Introduction and Overview  
Amazon EC2 (Elastic Compute Cloud) provides scalable computing capacity in the AWS cloud, allowing you to deploy and manage applications effortlessly. This document outlines the process to host a static website on an EC2 instance, making your content accessible over the internet.  

### Objectives  
- Deploy a static website using an EC2 instance.  
- Configure a web server (Apache or NGINX) to serve web content.  
- Transfer website files securely to the EC2 instance.  
- Make the website accessible via a public IP address.  

### Importance  
- **Cost-Effective**: Utilize the AWS Free Tier with t2.micro instances for budget-friendly hosting.  
- **Scalability**: Easily scale the infrastructure as traffic increases.  
- **Flexibility**: Full control over the server environment for custom configurations.  
- **Learning Opportunity**: Gain hands-on experience with cloud hosting and server management.  

### Steps  

#### Step 1: Launch an EC2 Instance  
- Go to the AWS Management Console.  
- Navigate to EC2 and click **Launch Instance**.  
- Choose an Amazon Machine Image (AMI) like **Amazon Linux 2**.  
- Select an instance type (e.g., **t2.micro** for free tier eligibility).  
- Configure instance details as required.  
- Add storage if needed.  
- Add a security group:  
  - Allow **HTTP (port 80)** for web traffic.  
  - Allow **SSH (port 22)** for secure server access.  
- Launch the instance and download the key pair (`.pem` file) for authentication.  

#### Step 2: Connect to Your EC2 Instance  
1. Open a terminal (or use PuTTY on Windows) in the location where the key pair is downloaded.  
2. Run the following command to connect:  
   ```sh  
   ssh -i /path/to/your-key.pem ec2-user@<EC2-Public-IP>  
   ```  
   - Replace `/path/to/your-key.pem` with the actual path to your key file.  
   - Replace `<EC2-Public-IP>` with your EC2 instance’s public IP.  


![Screenshot 2025-02-05 030707](https://github.com/user-attachments/assets/db527827-253c-4931-8212-a99efaf5d7ae)
#### Step 3: Install a Web Server (Apache or NGINX)  
##### For Apache:  
```sh  
sudo yum update -y  
sudo yum install httpd -y  
sudo systemctl start httpd  
sudo systemctl enable httpd  
```  

##### For NGINX (optional):  
```sh  
sudo amazon-linux-extras enable nginx1  
sudo yum install nginx -y  
sudo systemctl start nginx  
sudo systemctl enable nginx  
```  

#### Step 4: Upload Your Website Files  
1. Exit the SSH session.  
2. Use SCP to upload your website files from your local machine:  
   ```sh  
   scp -i /path/to/your-key.pem -r /path/to/your-website ec2-user@<EC2-Public-IP>:/tmp  
   ```  
3. SSH back into the EC2 instance:  
   ```sh  
   ssh -i /path/to/your-key.pem ec2-user@<EC2-Public-IP>  
   ```  

![Screenshot 2025-02-05 030902](https://github.com/user-attachments/assets/925a2c12-32c3-49bd-9da1-82e003597673)
#### Step 5: Move the File to the Web Server Directory  
1. Move the website files to the web server directory:  
   ```sh  
   sudo mv /tmp/index.html /var/www/html/  
   ```  
2. Restart the web server to apply changes:  
   ```sh  
   sudo systemctl restart httpd   # For Apache  
   ```  
   OR  
   ```sh  
   sudo systemctl restart nginx   # For NGINX  
   ```  

![Screenshot 2025-02-05 032607](https://github.com/user-attachments/assets/854287e8-5186-4f6d-9fd9-18bec001c756)
#### Step 6: Access Your Website  
Open a web browser and visit:  
```sh  
http://<EC2-Public-IP>  
```  
Replace `<EC2-Public-IP>` with your EC2 instance's public IP address to view your static website live.  

### Outcome  
Following these steps, you will have a successfully hosted static website on an AWS EC2 instance. Once setup is complete, you can access your website using:  
```sh  
http://<EC2-Public-IP>  
```

![Screenshot 2025-02-05 033403](https://github.com/user-attachments/assets/73460534-1760-420d-8f6a-a7b22a7a0415)
### Expected results:  
- A live static website served using Apache or NGINX.  
- Secure access to your EC2 instance for future updates.  
- Hands-on experience with AWS, EC2, and basic cloud hosting.  

If everything is set up correctly, your HTML page should load, confirming a successful deployment
