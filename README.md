# ☁️ AWS EC2 Web Server Deployment Lab

> **By Aryanraje Dhokale** — Cloud Enthusiast | Full Stack Developer | BTech CSE 2025  
> 📧 aryanrajedhokale03@gmail.com 

---

## 📋 Overview

This repository contains **3 hands-on AWS tasks** where I deployed web applications on EC2 instances using Apache and Nginx web servers on Amazon Linux and Ubuntu.

Each task includes:
- A running EC2 instance on AWS
- A configured web server (Apache / Nginx)
- Custom-built HTML web applications

---

## 🗂️ Repository Structure

```
aws-ec2-lab/
│
├── README.md                  ← You are here
├── LAB-GUIDE.html             ← Full step-by-step deployment guide
│
├── task1/                     ← Amazon Linux + Apache
│   ├── fashionhub.html        ← Fashion e-commerce app (Myntra-inspired)
│   └── connectpro.html        ← Professional network app (LinkedIn-inspired)
│
├── task2/                     ← Ubuntu + Nginx
│   ├── soundwave.html         ← Music streaming app (Spotify-inspired)
│   └── streammax.html         ← Video streaming app (Netflix-inspired)
│
└── task3/                     ← Amazon Linux + Nginx
    └── portfolio.html         ← My personal developer portfolio
```

---

## ✅ Task Breakdown

### Task 1 — Amazon Linux 2 + Apache + 2 Apps

| Item | Detail |
|---|---|
| EC2 OS | Amazon Linux 2023 |
| Web Server | Apache (httpd) |
| App 1 | `fashionhub.html` — Fashion e-commerce store |
| App 2 | `connectpro.html` — Professional networking site |
| URL Pattern | `http://<EC2-IP>/fashionhub.html` |

**Key commands used:**
```bash
sudo yum update -y
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
sudo cp fashionhub.html /var/www/html/
sudo cp connectpro.html /var/www/html/
```

---

### Task 2 — Ubuntu 22.04 + Nginx + 2 Apps

| Item | Detail |
|---|---|
| EC2 OS | Ubuntu Server 22.04 LTS |
| Web Server | Nginx |
| App 1 | `soundwave.html` — Music streaming platform |
| App 2 | `streammax.html` — Video streaming platform |
| URL Pattern | `http://<EC2-IP>/soundwave.html` |

**Key commands used:**
```bash
sudo apt update
sudo apt install -y nginx
sudo systemctl start nginx
sudo systemctl enable nginx
sudo cp soundwave.html /var/www/html/
sudo cp streammax.html /var/www/html/
```

---

### Task 3 — Amazon Linux + Nginx + Portfolio

| Item | Detail |
|---|---|
| EC2 OS | Amazon Linux 2023 |
| Web Server | Nginx |
| App | `portfolio.html` — Personal developer portfolio |
| URL Pattern | `http://<EC2-IP>/` (loads as index) |

**Key commands used:**
```bash
sudo yum update -y
sudo yum install -y nginx
sudo systemctl start nginx
sudo systemctl enable nginx
sudo cp portfolio.html /var/www/html/index.html
sudo systemctl restart nginx
```

---

## 🌐 Apps Built

| App | Type | Inspired By | Task |
|---|---|---|---|
| FashionHub | Fashion E-commerce | Myntra | Task 1 |
| ConnectPro | Professional Network | LinkedIn | Task 1 |
| SoundWave | Music Streaming | Spotify | Task 2 |
| StreamMax | Video Streaming | Netflix | Task 2 |
| Portfolio | Personal Website | Custom | Task 3 |

> ⚠️ All apps are **original designs** built from scratch for learning purposes. No copyrighted assets or code were used.

---

## 🛠️ Tech Stack

- **Cloud:** AWS EC2, Security Groups, IAM
- **OS:** Amazon Linux 2023, Ubuntu 22.04 LTS
- **Web Servers:** Apache (httpd), Nginx
- **Frontend:** HTML5, CSS3, Vanilla JavaScript
- **SSH:** Key-pair authentication, SCP file transfer

---

## 🚀 How to Deploy (Any Task)

1. **Launch EC2** on AWS Console with the correct OS
2. **Open ports** — SSH (22) and HTTP (80) in Security Group
3. **Connect via SSH:**
   ```bash
   chmod 400 your-key.pem
   ssh -i your-key.pem ec2-user@<PUBLIC-IP>   # Amazon Linux
   ssh -i your-key.pem ubuntu@<PUBLIC-IP>      # Ubuntu
   ```
4. **Install web server** (see task commands above)
5. **Upload HTML files** using SCP:
   ```bash
   scp -i your-key.pem filename.html ec2-user@<IP>:/home/ec2-user/
   sudo mv /home/ec2-user/filename.html /var/www/html/
   ```
6. **Open browser** → `http://<EC2-PUBLIC-IP>/filename.html`

---

## 👨‍💻 About Me

I'm **Aryanraje Dhokale**, a final-year BTech CSE student actively learning AWS and Cloud Computing. I have 4+ internship experiences in Java, React, Python, and Mobile Development.

- 🔗 [GitHub](https://github.com/aryanraje03)
- 🔗 [LinkedIn](https://www.linkedin.com/in/aryanraje192003)
- 📧 aryanrajedhokale03@gmail.com

---

*Built with hands-on practice on AWS Free Tier — 2025*
