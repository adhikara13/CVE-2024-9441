## Nortek Linear eMerge E3 Pre-Auth RCE PoC (CVE-2024-9441)

### Description:
This repository contains a Proof of Concept (PoC) exploit for **Nortek Linear eMerge E3** (CVE-2024-9441), which is vulnerable to **Remote Code Execution (RCE)** in a pre-authentication state. The vulnerability is triggered via a flaw in the password recovery feature, which allows an attacker to inject malicious PHP code into the system, leading to arbitrary code execution.

This PoC allows you to:
- Exploit the vulnerability by sending a crafted request.
- Execute arbitrary commands on the target system.
- Scan multiple targets using a mass scan feature from a list of IPs and ports.
- Perform single target scans using customizable parameters (IP, port, command, etc.).

### Vulnerability Details:
- **CVE**: [CVE-2024-9441](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2024-9441)
- **Affected Product**: Nortek Linear eMerge E3 (all versions prior to patch)
- **Type**: Pre-Auth Remote Code Execution
- **Attack Vector**: HTTP POST request exploiting the password recovery mechanism.

### Usage:

#### Requirements:
- Python 3.x
- `requests` library (`pip install requests`)

#### Single Scan Example:

```bash
python3 exploit.py --ip <target_ip> --port <port> --cmd "<command>"
```

#### Mass Scan Example:
Prepare a text file (e.g., `targets.txt`) with a list of target IPs and ports (one per line), then run:

```bash
python3 exploit.py --list targets.txt --cmd "<command>"
```

#### Notes:
- Replace `<command>` with the actual command you want to execute on the target.
- The PoC defaults to executing `/bin/ls -al /spider/web` if no command is provided.

### Disclaimer:
This PoC is for educational and research purposes only. Use responsibly and only against systems for which you have explicit permission to test. The author is not responsible for any misuse of this tool.

### Reference:
- https://ssd-disclosure.com/ssd-advisory-nortek-linear-emerge-e3-pre-auth-rce/