<img width="1920" height="386" alt="image" src="https://github.com/user-attachments/assets/35118e0e-f843-483e-b843-1bd48ca12d84" />


### Assigned 
- cr4cx

### case study
Detects a spike of commands like whoami, net user, and Get-ADUser, often used during AD domain discovery. Unless the commands are confirmed to be a part of IT activity or legitimate scripts, the device is likely compromised and requires immediate containment.

**flags**
- invoked commands: dir hostname whoami /priv net group **"Domain Admins"** /domain nltest /dclist:tryhackme.thm
- parent process: C:\Users\Public\ ***revshell.exe***

**comment**
- who    : NT AUTHORITY\SYSTEM
- what   : spike of commands like whoami, net user, and Get-ADUser
- when  : Mar 27th 2025 at 19:56 on DMZ-MSEXCHANGE-2013
- where : Windows Server 2012 R2
- why      : The activity is suspicious because w3wp.exe spawned revshell.exe which spawned cmd.exe including whoami/priv enumeration followed by domain controller enum. 
