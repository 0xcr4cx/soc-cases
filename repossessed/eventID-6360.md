Time of activity:
22 October 2026, 17:29:31

List of Affected Entities:
Host: THM-SREYES.tryhatmestudios.thm
Source IP: 10.60.10.20
Destination IP: 45.147.230.131
Process: powershell.exe (PID 14264)
User: NT AUTHORITY\SYSTEM

Reason for Classifying as True Positive:
Suspicious outbound TCP connection from PowerShell.
Alert indicates a correlation between archive creation and outbound data transfer.
Note: Confirm archive creation and destination reputation before final classification

Reason for Escalating the Alert:
Potential data exfiltration to an unverified external IP.
PowerShell running as SYSTEM increases the potential impact.

Recommended Remediation Actions:
Investigate the destination IP reputation.
Review PowerShell execution and archive contents.
Check outbound traffic volume and related connections.
If malicious activity is confirmed, isolate the host and block the destination.
Preserve relevant logs for incident response.

List of Attack Indicators:
Destination IP: 45.147.230.131
Destination port: 8067/TCP
Source IP: 10.60.10.20
Process: powershell.exe
Process ID: 14264
MITRE ATT&CK: T1041 — Exfiltration Over C2 Channel (potential; not confirmed)