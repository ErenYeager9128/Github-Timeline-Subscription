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
