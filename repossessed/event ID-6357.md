Time of activity:  10/22/2026 17:17:05.089

  
List of Affected Entities:

Host: THM-SREYES.tryhatmestudios.thm

Reason for Classifying as True Positive: The newly registered Windows service executes an anomalous command line (cmd.exe / c start /b powershell.exe ..) that runs a script from a world-writable directory (C:\Windows\Temp\) with execution policy bypassed, a hidden window, and configured to run under high privileges (LocalSystem), matching known attacker persistence patterns.

  

Reason for Escalating the Alert: The creation of a malicious system service using a compromised or abused service account (svc-mktshare) represents a high-severity persistence mechanism granting elevated system access, requiring immediate containment and threat hunting.

  

Recommended Remediation Actions:

Network- isolate the affected host ( THM-SREYES.tryhatmestudios.thm).

Stop and delete the malicious service (SvcUpdate).

Securely collect and analyze the script payload(C:\Windows\Temp\svchost_update.ps1)

Temporarily disable or reset credentials for TRYHATME\svc-mktshare.

Inspect Powershell operational logs (Event ID 4104) and logon logs (Event ID 4624) to trace initial access and lateral movement.

  

List of Attack Indicators:

T1543.003 (Create or Modify System Process: Windows Service)

T1059.001 (Command and Scripting Interpreter: PowerShell)

T1564.003 (Hidden Window)

Execution from World-Writable Directory (C:\Windows\Temp)

Evasive PowerShell flags (-NoP -NonI -W Hidden -ExecutionPolicy Bypass)

High-Privilege Execution (LocalSystem)