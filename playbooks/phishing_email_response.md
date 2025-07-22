# Phishing Email – Incident Response Playbook

🧠 Objective: Respond to and contain a reported phishing email before it leads to credential theft or malware execution.

---

## 🧪 Initial Detection

- User reports suspicious email  
- Detected by email filter (e.g., spoofed domain, suspicious link)  
- SOC alerted by SIEM/email security platform

---

## 🧰 Investigation Steps

1. **Gather Email Headers**  
   - Check sender domain, reply-to, SPF/DKIM/DMARC status  
   - Look for typosquatting or mismatched domains

2. **Inspect URL / Attachment**  
   - Use sandbox or VirusTotal  
   - Decode obfuscated URLs (base64, hex)

3. **Search Environment**  
   - Any other users received same email?  
   - Opened or clicked?

---

## 🛡️ Containment Actions

- Block sender/domain in email system  
- Remove email from inboxes (O365, Google Workspace)  
- Notify affected users

---

## 📄 Recovery

- Reset compromised accounts (if any)  
- Run endpoint scans  
- Monitor login attempts & unusual activity

---

## 🧠 Lessons Learned

- Update email filters / rules  
- Conduct phishing awareness training  
- Include sample in detection tuning

---

🎯 Mapped to MITRE ATT&CK: [Phishing – T1566.001](https://attack.mitre.org/techniques/T1566/001)
