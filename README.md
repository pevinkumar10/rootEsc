# Privilege Escalation Analysis Tool

## Overview
The Privilege Escalation Analysis Tool is designed to assist security professionals in auditing Linux systems for potential privilege escalation vectors. It automates system enumeration, identifying misconfigurations, vulnerable binaries, and other security risks.

## Features
- **User & Group Enumeration**: Lists all system users and groups, including current user privileges.
- **Kernel & System Information**: Displays OS version, kernel version, and system architecture.
- **SUID & SGID Binary Detection**: Identifies binaries with elevated privileges.
- **Sudo Privileges Check**: Lists available `sudo` privileges for the current user.
- **Writable Directories & Files**: Detects writable directories and files that could be abused.
- **Cron Job Analysis**: Identifies scheduled jobs running as root or other users.
- **Capabilities Enumeration**: Lists Linux capabilities assigned to binaries.
- **Process Analysis**: Identifies high-CPU consuming processes, processes running as root, and suspicious locations.

## Installation
Clone the repository and make the script executable:
```bash
git clone https://github.com/PkTheHacker10/rootEsc.git
cd rootEsc
```

## Usage
Run the tool as a normal user:
```bash
python3 rootESC.py -h
```

## Output
The tool will generate a structured report displaying:
- System information
- User privileges
- Writable files and directories
- Running processes
- Potential privilege escalation paths

## Example Output
```
[ ✓ ] Enumerating Id :
uid=1000(user1) gid=1000(users) groups=1000(users),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),101(lxd)

[ ✓ ] Enumerating Uname :
Linux user1 6.8.0-51-generic #52-Ubuntu SMP PREEMPT_DYNAMIC Thu Dec  5 13:09:44 UTC 2024 x86_64 x86_64 x86_64 GNU/Linux

[ ✓ ] Enumerating SudoVersion :
Sudo version 1.9.15p5
Sudoers policy plugin version 1.9.15p5
Sudoers file grammar version 50
Sudoers I/O plugin version 1.9.15p5
Sudoers audit plugin version 1.9.15p5

```

## Disclaimer
This tool is intended for security research and educational purposes only. Use it only on systems you own or have explicit permission to test.

## License
MIT License. See `LICENSE` for details.

