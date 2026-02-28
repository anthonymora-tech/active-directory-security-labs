# 🔐 Lab 2 – Domain Security Configuration  
## Commands Used

This document lists the commands used to configure and validate domain security settings within the Samba Active Directory environment.

---

## 📌 View Current Domain Password Policy

```bash
sudo samba-tool domain passwordsettings show
Displays:
	•	Password complexity status
	•	Minimum password length
	•	Password history
	•	Password age limits
	•	Account lockout settings

📌 Set Password Policy Requirements

sudo samba-tool domain passwordsettings set \
  --min-pwd-length=12 \
  --complexity=on \
  --history-length=5 \
  --min-pwd-age=1 \
  --max-pwd-age=60
Configures domain-wide password security controls.

📌 Configure Account Lockout Protection

sudo samba-tool domain passwordsettings set \
  --account-lockout-threshold=5 \
  --account-lockout-duration=15 \
  --reset-account-lockout-after=15
This enforces:
	•	Lockout after 5 failed attempts
	•	15-minute lockout duration
	•	Automatic reset window

📌 Verify Policy Changes
sudo samba-tool domain passwordsettings show
Used to confirm that new settings were applied successfully.

📌 Confirm Domain Admin Membership
sudo samba-tool group listmembers "Domain Admins"
Validates administrative role assignment.

📌 Check User Lockout Status
sudo samba-tool user show alice | grep lockout
Confirms whether account lockout enforcement is functioning.

📌 List Existing Group Policy Objects
sudo samba-tool gpo listall
Used to verify domain policy presence and linkage.

📌 Validate Computer Object Location in AD
sudo samba-tool computer show DESKTOP-E0E8QQP | grep distinguishedName
Ensures workstation is located within the intended OU structure.

🧠 Notes
	•	All commands were executed on the Samba Domain Controller
	•	Policies were validated using domain tools and user state checks
	•	Testing confirmed enforcement of lockout and password controls

⸻
🎯 Outcome

The domain now enforces enterprise-style authentication security, including password complexity requirements and protection against brute-force login attempts.
