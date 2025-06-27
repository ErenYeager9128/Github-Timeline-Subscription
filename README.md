# 🚀 GH-Timeline — Real-Time GitHub Timeline Email Updates

A modern PHP-based email verification and subscription engine that delivers **real-time GitHub timeline updates** to verified subscribers every 5 minutes. Built with 🔒 secure OTP verification, 📩 HTML emails, and a fully functional ⚙️ CRON automation — all database-free.

---

## 🌐 Live Flow

> ✉️ Email ➜ 🔐 Verify OTP ➜ ✅ Subscribed ➜ 🔄 Every 5min GitHub Updates ➜ 🔗 Unsubscribe (with OTP)

---

## 🔍 What Makes It Stand Out?

- 📫 **End-to-end Email Flow**: OTP verification, Timeline delivery, Unsubscribe confirmation
- 🔐 **No Database**: Pure file-based logic (`registered_emails.txt`)
- 📅 **Automated Updates**: GitHub Timeline fetched & mailed via CRON every 5 minutes
- 💎 **Minimal UI, Max Functionality**: Static visible forms (no conditional hiding) for testing ease
- 📜 **One-click Unsub**: Verified by OTP again before removal
- 🧠 **Submission-Safe**: No framework/library bloat (except PHPMailer)

---

## 📁 Directory Structure

```bash
src/
├── index.php              # Main UI for subscribing and OTP verification
├── unsubscribe.php        # Handles email opt-out via OTP
├── subscribe.php          # Sends verification OTP
├── verify.php             # Verifies OTP and registers email
├── cron.php               # Sends timeline updates to verified users
├── functions.php          # Core functional logic (mail, code gen, file ops)
├── registered_emails.txt  # Email list database (text only)
├── setup_cron.sh          # Automates CRON job setup
└── PHPMailer/             # SMTP email handler

💻 Setup & Run Instructions
✅ Prerequisites
PHP 8.x installed

CRON enabled (for Linux users)

Gmail App Password configured in functions.php

Localhost running (XAMPP/WAMP)

🔧 Setup
bash
Always show details

Copy
# Clone or unzip the repository
git clone https://github.com/yourusername/github-timeline-subscription.git
cd src/

# Give permission and set up CRON
chmod +x setup_cron.sh
./setup_cron.sh
▶️ Run Locally
bash
Always show details

Copy
# Start local server
php -S localhost:8000

# Then open in browser
http://localhost:8000
📦 Download ZIP
You can download the ready-to-run full source code ZIP here:

🔗 Click to Download

Or use:

bash
Always show details

Copy
wget https://github.com/yourusername/github-timeline-subscription/archive/refs/heads/main.zip
unzip main.zip
💌 Email Templates
📥 OTP Email
html
Always show details

Copy
<p>Your verification code is: <strong>123456</strong></p>
🔄 GitHub Update Email
html
Always show details

Copy
<h2>GitHub Timeline Updates</h2>
<table border="1">
  <tr><th>Event</th><th>User</th></tr>
  <tr><td>Push</td><td>testuser</td></tr>
</table>
<p><a href="unsubscribe_url" id="unsubscribe-button">Unsubscribe</a></p>
🗑️ Unsubscribe Code Email
html
Always show details

Copy
<p>To confirm unsubscription, use this code: <strong>654321</strong></p>
🧠 Dev Notes
✅ No DB used — just plain text files

✅ Verified form structure for assignment submission

✅ CRON fully working & testable

✅ OTPs are 6-digit and securely session-tracked

