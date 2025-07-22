# Suspicious PowerShell Execution – Incident Response Playbook

🧠 Objective: Investigate and respond to unusual or potentially malicious PowerShell activity on a Windows host.

---

## 🧪 Initial Detection

- Alert triggered by PowerShell script block logging (EventCode 4104)  
- Keywords found: "Invoke", "FromBase64String", "DownloadString"  
- Detection via SIEM or EDR tool

---

## 🔍 Investigation Steps

1. **Review Command Line**  
   - Is it encoded? (Base64)  
   - Does it reference external URLs or known payloads?

2. **Check Process Tree**  
   - Parent process of PowerShell (e.g., Word, Excel)  
   - Child processes spawned (e.g., cmd, rundll32)

3. **Search Host Activity**  
   - Any known malware indicators?  
   - Files written to disk? Registry keys modified?

4. **Review User Behavior**  
   - Was it an admin or standard user?  
   - Is this behavior normal for that account?

---

## 🛡️ Containment Actions

- Kill malicious PowerShell processes  
- Isolate host from network  
- Preserve memory + disk for forensic capture

---

## 📄 Recovery

- Remove any payloads/scripts  
- Patch exploited software  
- Reimage if persistence is confirmed

---

## 💡 Lessons Learned

- Improve alerting rules for encoded or obfuscated PowerShell  
- Implement PowerShell logging + script block logging GPO  
- Educate users on macro-based threats and unsafe documents

---

🎯 Mapped to MITRE ATT&CK: [T1059.001 – PowerShell](https://attack.mitre.org/techniques/T1059/001)
