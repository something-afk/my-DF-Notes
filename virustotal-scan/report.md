# VirusTotal Analysis Report

## 📁 File Info
- Filename: malware_sample.zip
- File inside: malware_sample.docx
- Hashes:
  - MD5: f1fd4cf59c5cfb5e4ab5fd8570889fdb 
  - SHA1: 48543fec63c090153308892c3cdfc411979c4b45
  - SHA256: ae2a513b61febc225d5e374ab22dba754a3d38e49b7bbd442fe3f9bab16b8fb1

## 🧪 Detection
| Engine              | Detection                               |
|---------------------|-----------------------------------------|
| AhnLab-V3           | Malware/Win.Kryptik.C5784104            |
| Alibaba             | Trojan:MSIL/Taskun.cf3a01e2             |
| AliCloud            | Trojan:MSIL/Egairtigado.Gen             |
| ALYac               | Trojan.GenericKDZ.112786                |
| Arcabit             | Trojan.Generic.D1B892                   |
| Arctic Wolf         | Unsafe                                  |
| Avast               | Win32:MalwareX-gen [Pws]                |
| AVG                 | Win32:MalwareX-gen [Pws]                |
| Avira (no cloud)    | TR/AD.SnakeStealer.lzrbr                |
| BitDefender         | Trojan.GenericKDZ.112786                |

## 📡 Network Indicators
Domains Flagged-
- api.telegram.org
dyndns.org
reallyfreegeoip.org

Ip Flagged-
104.21.112.1
104.21.16.1
104.21.32.1
104.21.48.1
104.21.64.1
104.21.80.1
104.21.96.1
132.226.247.73
132.226.8.169
149.154.167.220

## 📊 Behavioral Summary
- Executes malicious payload (file.exe) from the user’s desktop.

Abuses PowerShell to add Windows Defender exclusion for the malicious file, bypassing detection.

Spawns multiple system processes (svchost.exe, services.exe, lsass.exe) to blend in with normal system activity.

Accesses Windows Defender libraries and key system directories (C:\ProgramData, C:\ProgramData\Microsoft\Windows\Caches).

Drops log files related to malicious activity in %LOCALAPPDATA%\Microsoft\CLR_v4.0_32\UsageLogs.

Modifies or interacts with Windows AppRepository and cache databases, possibly to alter app behavior or hide presence.


## 🗣️ Community Insight
- Votes, user comments
- Votes: 36/94 engines flagged as malicious.  
- User comments: Flags indicate info-stealer behavior, Telegram C2 usage, suspicious .NET obfuscation.

## 🔐 Public Link
- https://www.virustotal.com/gui/file/ae2a513b61febc225d5e374ab22dba754a3d38e49b7bbd442fe3f9bab16b8fb1/relations

