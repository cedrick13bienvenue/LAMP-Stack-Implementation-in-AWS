# Project: LAMP Stack Implementation on AWS

## Project Overview

This project involves the manual deployment and configuration of a **LAMP Stack** (Linux, Apache, MySQL, PHP) on a virtualized Amazon EC2 instance. This implementation focuses on granular administration of each layer, providing insight into infrastructure management, security group orchestration, and server-side scripting integration.

---

## Phase 1: Provisioning the Compute Engine (Linux & Apache)

The foundation of the stack is an EC2 Instance running **Ubuntu 24.04 LTS**. Apache serves as the web server, responsible for listening to incoming HTTP requests and serving content to client browsers.

### 1.1 Installation and Service Management

To prepare the environment, synchronize the local package index with global Ubuntu repositories before installing the Apache service:

- **Update package list**

  ```bash
  sudo apt update
  ```

- **Install Apache**

  ```bash
  sudo apt install apache2
  ```

- **Verify service status**

  ```bash
  sudo systemctl status apache2
  ```

> **Expected Output:** The terminal should display a green indicator and the text **"Active: active (running)"**.
> ![Installation and Service Management](screenshoots/1.png)

1.2 Networking and Verification

Configure Security Group: Open Port 80 (HTTP) to 0.0.0.0/0 in the AWS EC2 Security Group.

> ![Networking and Verification](screenshoots/2.png)

- **Public IP Access:** Navigate to the following URL in your browser:

  ```text
  http://<YOUR_PUBLIC_IP>:80
  ```

> **Web Preview:** The **Apache2 Ubuntu Default Page** with the red header **"It works!"** should appear.
> ![Apache2 Ubuntu Default Pag](screenshoots/3.png)

---

## Phase 2: Data Persistence Layer (MySQL)

A relational database is required to store application data such as user records and state information.

### 2.1 Installation

- **Install MySQL Server**

  ```bash
  sudo apt install mysql-server
  ```

- **Access MySQL Shell**

  ```bash
  sudo mysql
  ```

> **Expected Output:** The MySQL administrative prompt `mysql>` should appear.
> ![Apache2 Ubuntu Default Pag](screenshoots/4.png)

### 2.2 Security Hardening

Run MySQL's built-in security script to remove insecure defaults:

```bash
sudo mysql_secure_installation
```

> **Expected Output:** After completing the prompts, the script should finish with **"Success. All done!"**.
> ![Apache2 Ubuntu Default Pag](screenshoots/_4.png)

---
