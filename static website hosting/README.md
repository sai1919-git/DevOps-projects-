#  Static Website Deployment on AWS EC2 using Nginx

##  Project Title
Static Website Hosting on AWS EC2 (Ubuntu + Nginx + Git)

---

##  Project Goal

The goal of this project is to deploy a static HTML website on an AWS EC2 instance using Nginx web server and Git for version control.

This project demonstrates basic cloud provisioning, Linux server management, Git operations, and web server configuration — essential skills for a DevOps Engineer.

---

##  Tools & Technologies Used

- AWS EC2 (Ubuntu Server)
- Nginx Web Server
- Git & GitHub
- Linux (Ubuntu)
- SSH
- HTML (Static Website)

---

##  Architecture

Local System  
    |
GitHub Repository  
    |
AWS EC2 Instance (Ubuntu)  
    |
Nginx Web Server  
    |
Public IP (Live Website)

---

## What i Did (Step-by-Step Overview)

1. Created a static HTML website (`index.html`).
2. Pushed the project to GitHub repository.
3. Launched an EC2 instance (Ubuntu) on AWS.
4. Configured Security Group to allow:
   - Port 22 (SSH)
   - Port 80 (HTTP)
5. Connected to EC2 using SSH.
6. Installed Nginx on Ubuntu.
7. Verified Nginx configuration root directory.
8. Cloned GitHub repository into EC2.
9. Moved project files to `/var/www/html`.
10. Set proper permissions.

## scripting

Connect to EC2 via SSH
```bash
chmod 400 your-key.pem
ssh -i aws-login.pem ubuntu@65.2.171.222
 Update System
sudo apt update
```

### Install Nginx
```bash
sudo apt install nginx -y


Start & enable Nginx:

sudo systemctl start nginx
sudo systemctl enable nginx


Check status:

sudo systemctl status nginx

Install Git
sudo apt install git -y


Check version:

git --version

Move to Correct Web Root

cd /var/www/html


Remove default files:

sudo rm -rf *
```

### Clone GitHub Repository
```bash
sudo git clone https://github.com/sai1919-git/DevOps-projects-.git
```
 Move Project Files from Subfolder

Because folder name had spaces:

sudo mv "DevOps-projects-/static website hosting/"* .

### Remove Extra Repository Folder
```bash
sudo rm -rf DevOps-projects-
```
### Set Correct Permissions (Ubuntu Specific)
```bash
sudo chown -R www-data:www-data /var/www/html
```
### Restart Nginx
```bash
sudo systemctl restart nginx
```
### Access Website
```bash
Open in browser:
http://65.2.171.222
```
