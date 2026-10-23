## Anomalous Credential Vault Access

Time of activity:
Oct 22, 2026, at 17:16

List of Affected Entities:
Host: THM-MSMITH.tryhatmestudios.thm
User: TRYHATME\m.smith
Process: VaultCmd.exe (PID 10872)
Parent process: powershell.exe (PID 9356)
Script: svchost_update.ps1

Reason for Classifying as True Positive:
Hidden PowerShell executed a script from a temporary directory.
The script launched VaultCmd.exe to enumerate Windows stored credentials.
PowerShell used ExecutionPolicy Bypass, indicating suspicious execution.

Reason for Escalating the Alert:
Potential credential theft and lateral movement.
Possible compromise of the user's account and host.
Stored credentials may enable unauthorised access to other systems.

Recommended Remediation Actions:
Isolate the affected host.
Preserve PowerShell and Sysmon logs for investigation.
Analyse svchost_update.ps1 and identify its origin.
Reset potentially exposed credentials and revoke active sessions.
Investigate related logins and lateral movement.

List of Attack Indicators:
VaultCmd.exe enumerating Windows credentials.
Hidden PowerShell execution.
-ExecutionPolicy Bypass
Script path: C:\Users\MC0CD~1.SMI\AppData\Local\Temp\svchost_update.ps1
User: TRYHATME\m.smith
MITRE ATT&CK: T1555.004 — Windows Credential Manager
