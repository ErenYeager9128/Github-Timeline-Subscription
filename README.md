# 🚀 GH-Timeline — GitHub Email Subscription System

A powerful PHP-based email subscription platform where users register using email, receive a secure OTP, and start receiving GitHub timeline updates every 5 minutes via CRON-triggered HTML emails. Includes a smart unsubscribe mechanism, no DB, no frameworks — just clean, secure PHP magic.

---

## 🌐 Live Flow

> ✉️ Email ➜ 🔐 Verify OTP ➜ ✅ Subscribed ➜ 🔄 Every 5min GitHub Updates ➜ 🔗 Unsubscribe (with OTP)

---

## ✨ Features

- 🔐 Email OTP Verification (6-digit code via Gmail SMTP)
- 📥 GitHub Timeline updates every 5 minutes (CRON)
- 🧼 Clean Unsubscribe with email confirmation
- 📄 Emails sent in HTML format
- 🛠 Pure PHP — no frameworks, no DBs
- 📜 Flat-file storage using `registered_emails.txt`
- 🚫 No Mailhog — real emails via Gmail (App Password)

---

## 💻 Setup & Installation

> ⚠️ Make sure PHP (≥8.0) and CRON are installed.  
> Recommended to run on Linux/macOS or WSL for CRON compatibility.

### ⬇️ Step 1: Clone or Download

Or download as ZIP from the GitHub repo and extract it:

Edit
📦 Download ZIP → Extract → Open in VS Code / PHP server

### 📁 Step 2: Configure PHPMailer
Inside /src/functions.php, make sure these are correct:

php
Copy
Edit
$mail->Host = 'smtp.gmail.com';
$mail->Username = 'your-email@gmail.com';
$mail->Password = 'your-app-password'; // NOT your Gmail password
$mail->setFrom('your-email@gmail.com', 'GitHub Email Bot');
💡 Use Gmail App Passwords (go to your Google account > Security > App passwords)

Make sure PHPMailer/ folder exists inside root directory.

### ⚙️ Step 3: Start Localhost Server
bash
Copy
Edit
php -S localhost:8000 -t src
Then open: http://localhost:8000

## 🔄 CRON Job Setup
🛠 Auto-Setup Script
Just run the bash script provided:

bash
Copy
Edit
cd src
chmod +x setup_cron.sh
./setup_cron.sh
This sets up a cron job that triggers cron.php every 5 minutes and sends timeline updates.


[Github-Timeline-Subscription.zip](https://github.com/user-attachments/files/20956126/Github-Timeline-Subscription.zip)
