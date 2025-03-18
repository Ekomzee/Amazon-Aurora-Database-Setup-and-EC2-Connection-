# Amazon-Aurora-Database-Setup-and-EC2-Connection-
This repository contains a step-by-step guide on how to create an Amazon Aurora database and securely connect it to an EC2 instance.
This guide covers:  
✔ Creating and deploying a **web application** on an **EC2 instance**  
✔ Connecting the **web app to a MySQL database (Amazon RDS/Aurora)**  
✔ Upgrading the web app to a new version  
✔ Testing the updated web app  

---

## Prerequisites  
- **AWS account**  
- **Amazon EC2 instance** (for hosting the web app)  
- **Amazon RDS or Aurora MySQL database**  
- **Security Groups** (allowing traffic between the EC2 and RDS)  
- **SSH key** to access the EC2 instance  
- **Git & Web Server (Apache/Nginx) installed**  

---

## **1. Deploying a Web App on an EC2 Instance**  
### **Step 1: Launch an EC2 Instance**  
1. Navigate to **AWS EC2 Console** → Click **Launch Instance**.  
2. Select an **Amazon Linux 2** or **Ubuntu** AMI.  
3. Choose an **instance type** (e.g., `t2.micro` for Free Tier).  
4. Create/select an **SSH Key Pair** to access the instance.  
5. Configure **Security Groups**:  
   - Allow **HTTP (port 80)** and **HTTPS (port 443)** for web traffic.  
   - Allow **SSH (port 22)** for remote access.  
6. Click **Launch Instance** and wait for it to start.  

---

### **Step 2: Install Web Server & App Dependencies**
#### **For Apache (PHP-based apps)**
1. SSH into your EC2 instance:  
   ```sh
   ssh -i your-key.pem ec2-user@your-ec2-public-ip

## **Step 3: Install Apache and PHP ##
sudo yum update -y
sudo yum install -y httpd php php-mysqlnd

##Starting and enabling Apache#
sudo systemctl start httpd
sudo systemctl enable httpd
