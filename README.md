# 🔧 Linux Server Home Lab

## 📌 Overview

This project demonstrates the deployment and configuration of a Linux
server using Ubuntu Server in a virtualized environment. It includes web
server setup, remote access configuration, basic security
implementation, and real-world troubleshooting.

------------------------------------------------------------------------

## 🧰 Technologies Used

-   Ubuntu Server (Linux)
-   VirtualBox
-   Nginx Web Server
-   SSH (Secure Shell)
-   Fail2Ban
-   Bash / Linux CLI

------------------------------------------------------------------------

## ⚙️ Environment Setup

-   **Platform:** VirtualBox
-   **Operating System:** Ubuntu Server
-   **Network:** Local network (private IP)
-   **Access Method:** SSH from host machine

------------------------------------------------------------------------

## 🌐 Web Server Configuration (Nginx)

### 🔹 Installation

``` bash
sudo apt update
sudo apt install nginx -y
```

### 🔹 Verification

``` bash
sudo systemctl status nginx
```

### 🔹 Access

Open browser:

    http://<your-server-ip>

------------------------------------------------------------------------

## 🔐 SSH Configuration

### 🔹 Enable SSH

``` bash
sudo systemctl enable ssh
sudo systemctl start ssh
```

### 🔹 Test Remote Access

From host machine:

``` bash
ssh username@<server-ip>
```

### 🔹 Basic Hardening

-   Disabled root login
-   Controlled authentication settings

------------------------------------------------------------------------

## 🛡️ Security Implementation (Fail2Ban)

### 🔹 Installation

``` bash
sudo apt install fail2ban -y
```

### 🔹 Configuration

Created jail configuration:

``` ini
[sshd]
enabled = true
port = ssh
maxretry = 3
bantime = 600
findtime = 600
```

### 🔹 Testing

-   Simulated brute-force attack using multiple failed SSH logins
-   Observed logs and behavior using:

``` bash
sudo journalctl -u fail2ban -f
```

------------------------------------------------------------------------

## 🧪 Troubleshooting & Issues Resolved

-   Fixed package installation issues (apt update errors)
-   Diagnosed SSH connection problems (authentication & network)
-   Resolved IP and network configuration issues
-   Debugged Fail2Ban detection and logging behavior

------------------------------------------------------------------------

## 📊 Key Learnings

-   Linux server deployment and management\
-   Web server setup and service control\
-   SSH configuration and remote access\
-   Log monitoring and troubleshooting\
-   Basic system security practices
