:::writing{variant=“standard” id=“lab2readme01”}

Active Directory Security Lab – Account Policies

This lab demonstrates how to harden domain security by configuring password policies and account lockout protections using a Samba-based Active Directory Domain Controller.

🎯 Objectives
	•	Enforce strong password requirements
	•	Configure account lockout protections
	•	Verify domain administrator membership
	•	Validate lockout behavior on user accounts

🧰 Environment
	•	Ubuntu Server running Samba AD DC
	•	Windows 11 client joined to domain
	•	Domain: lab.local

🔐 Security Controls Implemented
	•	Minimum password length: 12 characters
	•	Password complexity: Enabled
	•	Password history: 5 previous passwords remembered
	•	Lockout threshold: 5 failed attempts
	•	Lockout duration: 15 minutes
	•	Reset counter after: 15 minutes

✅ Outcome

The domain now enforces modern password security controls and prevents brute-force login attempts through account lockouts.

📂 Documentation
	•	Lab2-Domain-Security.md → Full walkthrough & explanation
	•	Commands-Used.md → All commands executed in the lab
:::
