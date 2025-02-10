## Deploy a Web Application on the Cloud: **Write a Python Flask application and deploy it on your cloud VM. Configure the firewall to allow HTTP traffic.**

### Introduction and Overview
This document outlines the process of deploying a simple Python Flask web application on an AWS EC2 instance. The guide covers creating a Flask app, transferring it to the EC2 instance, configuring security groups to allow HTTP traffic, and running the application successfully.

### Objectives
- **Develop a basic Python Flask web application.**
- **Deploy the Flask app on an AWS EC2 instance.**
- **Configure security settings to allow HTTP traffic on port 5000.**
- **Verify the app's accessibility over the internet.**

### Importance
- **Cloud Deployment Skills:** Demonstrates the ability to deploy applications in a real cloud environment.
- **Web Accessibility:** Ensures the app can be accessed from anywhere globally.
- **Security Configuration:** Provides hands-on experience with configuring security groups and firewall rules.
- **Practical AWS Knowledge:** Enhances practical understanding of AWS EC2, SSH, and server management.

### Steps

#### STEP 1: Write a Simple Flask Application
Create a Python file named `app.py` with the following code:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Hello, World!"

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```
![Screenshot 2025-02-07 024505](https://github.com/user-attachments/assets/d5792f9a-7ac8-4f4c-991f-346179a515aa)

#### STEP 2: Prepare Your EC2 Instance

1. Connect to your EC2 instance:
    ```bash
    ssh ec2-user@your-ec2-public-ip
    ```
![Screenshot 2025-02-07 025410](https://github.com/user-attachments/assets/479a0baa-0ac4-43c2-aa50-efaa64d6afe9)

2. Update packages:
    ```bash
    sudo yum update -y
    ```
![Screenshot 2025-02-07 025514](https://github.com/user-attachments/assets/45820f43-6165-4568-8677-25b2f143569e)

3. Install Python and pip:
    ```bash
    sudo yum install python3 python3-pip -y
    ```
![Screenshot 2025-02-07 025629](https://github.com/user-attachments/assets/28ad0777-f3aa-4075-a202-54e57eb973b4)

4. Install Flask:
    ```bash
    pip3 install Flask
    ```
![Screenshot 2025-02-07 025800](https://github.com/user-attachments/assets/db81e7be-d068-4738-8e23-8b024607ad4f)

#### STEP 3: Transfer the Flask App to the EC2 Instance

From your local machine, open a terminal and run the following command:

```bash
scp -i "path/to/key.pem" "D:/path/to/app.py" ec2-user@your-ec2-public-ip:/home/ec2-user/
```
![Screenshot 2025-02-07 032202](https://github.com/user-attachments/assets/57c07020-699c-4f29-8576-e78bdd9643c6)

Replace the directories with your key pair and Flask app location, and your EC2 public IP.
#### STEP 4: Run the Flask App on the EC2 Instance

Run the Flask app on the EC2 instance:

```bash
python3 app.py
```

#### STEP 5: Configure the Firewall (Security Group Settings)

1. Go to AWS Console → EC2 Dashboard → Security Groups → Inbound Rules → Edit.
2. Add a rule:
    - **Type:** Custom TCP
    - **Protocol:** TCP
    - **Port Range:** 5000
    - **Source:** 0.0.0.0/0 (or specific IP for more security)
3. Save the rules.

#### STEP 6: Access the Application

Open a browser and go to:

```
http://your-ec2-public-ip:5000
```
![Screenshot 2025-02-10 093804](https://github.com/user-attachments/assets/a2f505cb-4e9e-4be4-b53d-6222fb1c32ce)

You should see "Hello, World!" displayed.

### Outcomes
- Successfully developed and deployed a Python Flask web application on an AWS EC2 instance.
- Gained hands-on experience in configuring AWS security groups to allow HTTP traffic.
- Demonstrated the ability to transfer files to a remote server using SCP.
- Enhanced understanding of cloud deployment and server management.
- Successfully accessed the web application from a remote location, ensuring global accessibility.
