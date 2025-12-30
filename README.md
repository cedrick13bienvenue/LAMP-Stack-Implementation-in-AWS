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
