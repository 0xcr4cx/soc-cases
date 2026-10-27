<img width="1874" height="956" alt="Screenshot From 2026-10-26 23-22-42" src="https://github.com/user-attachments/assets/6032256e-015c-4de6-b52f-be9c4a058270" />
<img width="1663" height="910" alt="Screenshot From 2026-10-26 23-36-12" src="https://github.com/user-attachments/assets/98d36fd4-eedc-4cde-96fe-320d5a170de8" />
<img width="1658" height="910" alt="image" src="https://github.com/user-attachments/assets/db0b1155-49a4-443b-bebd-427f1d9bc47e" />


#### Upload the data attached to this task and create an index "VPN_Logs". How many events are present in the log file?
```
index=VPN_Logs
| stats count



index=VPN_Logs
| spath
| search UserName="Maleena"
| stats count

index=VPN_Logs
| spath
| search Source_ip="107.14.182.38"
| stats values(UserName) as UserName count

index=VPN_Logs
| spath
| search Source_Country!="France"
| stats count

index=VPN_Logs
| spath
| search Source_ip="107.3.206.58"
| stats count
```
Upload the data attached to this task and create an index "VPN_Logs". How many events are present in the log file?
- 2862

How many log events are captured by the user Maleena?
- 60

What is the username associated with IP 107.14.182.38?
- Smith

What is the number of events that originated from all countries except France?
- 2814

How many VPN events were associated with the IP 107.3.206.58?
- 14




