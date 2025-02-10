## Implement Auto-scaling in the Cloud: Set up an auto-scaling group for your cloud VMs to handle variable workloads.

### Introduction and Overview
Auto-scaling in AWS is a powerful feature that enables cloud environments to automatically adjust computing resources based on dynamic workloads. This ensures applications maintain performance while optimizing costs. By automatically increasing or decreasing the number of EC2 instances, AWS Auto Scaling helps achieve high availability and efficient resource utilization.

### Objectives
- **To set up an Auto Scaling Group (ASG) in AWS.**
- **To automate the scaling of EC2 instances based on workload demands.**
- **To improve application availability and reliability.**
- **To optimize cloud resource utilization and reduce costs.**

### Importance
- **Cost Efficiency:** Reduces costs by scaling down unused resources.
- **High Availability:** Maintains application uptime even during traffic spikes.
- **Performance Optimization:** Ensures consistent performance under varying loads.
- **Automation:** Eliminates manual intervention for scaling resources.

### Steps

#### STEP 1: Create a Launch Template
- Go to the **AWS Management Console** → **EC2** → **Launch Templates** → **Create Launch Template**.
- Provide a name for your template.
- Choose the **Amazon Linux 2 AMI**.
- Select the instance type **t2.micro**.
- Configure key pair and security group (allow **HTTP, HTTPS, and SSH**).
- Do not add a subnet during this process.
- Under **Advanced Details**, add the following User Data script:

![Screenshot 2025-02-10 101349](https://github.com/user-attachments/assets/a58521b3-6a01-46f0-84c9-8ddccb78c4b2)
![Screenshot 2025-02-10 101514](https://github.com/user-attachments/assets/0bfa0cf3-729a-4734-b22a-ad66748c7987)
![Screenshot 2025-02-10 101539](https://github.com/user-attachments/assets/3fcdf932-da2f-4ff8-b2e2-afe4a73450fe)

```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
```
![Screenshot 2025-02-10 101724](https://github.com/user-attachments/assets/bcbca439-96ba-4544-94d6-6b8780c162e3)

- Review and create the launch template.

![Screenshot 2025-02-10 101741](https://github.com/user-attachments/assets/1aa49597-151a-42e4-9de5-fe72d562ac1f)

### STEP 2: Create an Auto Scaling Group (ASG)
- Go to **Auto Scaling Groups** → **Create Auto Scaling Group**.

![Screenshot 2025-02-10 102206](https://github.com/user-attachments/assets/76ce4dd8-82cc-4039-b1e6-2ce67c93118a)

- Provide a name for the ASG and select the launch template created earlier.
- Choose the **VPC** and select any subnets.

![Screenshot 2025-02-10 102240](https://github.com/user-attachments/assets/bc318e44-c59c-4693-b2cf-cedb190a66fb)

- Set desired, minimum, and maximum capacity (e.g., **1 min, 2 desired, 4 max**).
- Add a **Target Tracking Scaling Policy**:
  1. **Metric:** Average CPU Utilization
  2. **Target Value:** 40%
  3. **Warm-up Time:** 300 seconds
- Review and create the **Auto Scaling Group**.

![Screenshot 2025-02-10 102354](https://github.com/user-attachments/assets/94fcc0bd-13cb-4cab-aa14-912881b702ea)
![Screenshot 2025-02-10 102425](https://github.com/user-attachments/assets/1b3bcc40-605e-4b36-8b55-dae243fac2f5)

#### STEP 3: Test the Auto-Scaling Setup
1. After the ASG launches an instance, connect to it via **SSH** using the key pair.
2. Install the stress tool to simulate high CPU load:

```bash
sudo yum install stress -y
```

![Screenshot 2025-02-10 102851](https://github.com/user-attachments/assets/7b767160-19b6-4f17-8bbf-9ad883ef5c5a)

3. Generate CPU stress to trigger scaling:

```bash
stress --cpu 2 --timeout 300
```

![Screenshot 2025-02-10 103031](https://github.com/user-attachments/assets/32c9f4c2-085d-4b96-a0a2-f21fc3cf2ae8)

4. Monitor scaling activities within the **Auto Scaling Group → Monitoring**.

![Screenshot 2025-02-10 103050](https://github.com/user-attachments/assets/e70235a8-7bfd-497f-b844-52d1dd730647)
5. An instance will be launched due to one of the running instances reaching its limit due to the stress test.

### Outcomes
- Successfully created and configured an **Auto Scaling Group** in AWS.
- Gained hands-on experience in automating **EC2 instance scaling** based on workload demands.
- Improved understanding of **AWS monitoring tools** to track scaling activities.
- Optimized cloud resource usage by ensuring instances scale up and down as needed.
- Enhanced knowledge of **AWS Auto Scaling policies** and their real-world applications.

---
