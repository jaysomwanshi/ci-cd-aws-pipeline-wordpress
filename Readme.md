# CI/CD AWS Pipeline for WordPress

This project demonstrates a **Continuous Integration and Continuous Deployment (CI/CD)** setup for a WordPress website hosted on **AWS EC2** with **Nginx**, **PHP**, and **MySQL/MariaDB**. The deployment is automated using **GitHub Actions** to ensure seamless code updates from the repository to the live server.

---

## 🚀 Project Overview
The goal of this lab/project is to:
- Host a WordPress site on AWS EC2 using the LEMP stack (Linux, Nginx, MySQL/MariaDB, PHP).
- Automate deployment using GitHub Actions.
- Practice DevOps skills like server provisioning, SSH key configuration, environment setup, and deployment scripting.

---

## 🛠️ Tech Stack
- **AWS EC2** (Ubuntu 22.04 LTS)
- **Nginx** (Web server)
- **MariaDB/MySQL** (Database)
- **PHP** (Backend for WordPress)
- **GitHub Actions** (CI/CD automation)
- **Rsync / SCP** (File transfers)
- **SSH Keys** (Secure server access)

---

## 📂 Repository Structure

---

## ⚙️ CI/CD Workflow
1. **Push to main branch** → GitHub Actions workflow is triggered.
2. Workflow connects to AWS EC2 via **SSH** using stored secrets.
3. Files are synced with `/var/www/html/wordpress` on the server using `rsync`.
4. Optionally run database migration or cache clearing commands.
5. Deployment completed automatically — no manual intervention required.

---

## 📋 Prerequisites
Before using this project, ensure you have:
- An AWS EC2 instance running Ubuntu 22.04.
- Installed **Nginx, MariaDB, PHP** (LEMP stack).
- Domain DNS A record pointing to EC2 public IP.
- SSH key pair set up between GitHub Actions and your server.

---

## 🔑 Environment Variables (GitHub Secrets)
Set these secrets in your GitHub repository:
- `HOST` → Public IP or domain of your EC2 instance.
- `USERNAME` → SSH user (e.g., `ubuntu`).
- `PRIVATE_KEY` → Your private SSH key.
- `REMOTE_PATH` → Path on server (e.g., `/var/www/html/wordpress`).

---

## 📦 Deployment Instructions
1. **Clone the repo**  
   ```bash
   git clone https://github.com/jaysomwanshi/ci-cd-aws-pipeline-wordpress.git
   cd ci-cd-aws-pipeline-wordpress
