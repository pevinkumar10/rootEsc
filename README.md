# RootESC the privilege Escalation Analysis Tool

## Overview
The tool rootESC is a privilege escalation analysis tool created by **Pevinkumar A** to find privilege escalation vector .

## Features
- **User & Group Enumeration**: Lists all system users and groups, including current user privileges.
- **Kernel & System Information**: Displays OS version, kernel version, and system architecture.
- **SUID & SGID Binary Detection**: Identifies binaries with elevated privileges.
- **Sudo Privileges Check**: Lists available `sudo` privileges for the current user.
- **Writable Directories & Files**: Detects writable directories and files that could be abused.
- **Cron Job Analysis**: Identifies scheduled jobs running as root or other users.
- **Capabilities Enumeration**: Lists Linux capabilities assigned to binaries.
- **Process Analysis**: Identifies high-CPU consuming processes, processes running as root, and suspicious locations.
## Tool structure 
```
.
├── README.md
└── rootEsc
    ├── modules                      # This folder contains Modules that are required by rootESC. 
    │   ├── cli
    │   │   ├── cli.py
    │   │   └── __init__.py
    │   ├── core.py                  # This the file contains core logic and functions of the rootESC. 
    │   ├── __init__.py
    │   ├── scripts                  # It contains all the scripts that is used to enumerate privilege escalation vectors.
    │   │   ├── 1_system
    │   │   │   ├── 01_Id.sh
    │   │   │   ├── 02_Uname.sh
    │   │   │   ├── 03_SudoVersion.sh
    │   │   │   ├── 04_SudoPrivCheck.sh
    │   │   │   ├── 05_AllUsers.sh
    │   │   │   └── 06_RootUser.sh
    │   │   ├── 2_files
    │   │   │   ├── 07_SUID.sh
    │   │   │   ├── 08_SGID.sh
    │   │   │   ├── 09_WritableEnvDir.sh
    │   │   │   ├── 10_CronJobs.sh
    │   │   │   └── 11_Capability.sh
    │   │   ├── 3_process
    │   │   │   ├── 12_CpuConsumingProcesses.sh
    │   │   │   ├── 13_ProccessWithSuspiciousLocations.sh
    │   │   │   └── 14_ProcRunningAsRoot.sh
    │   │   ├── 4_network
    │   │   │   └── 15_UnusualNetworkCon.sh
    │   │   └── 5_log
    │   │       └── 16_FailedPasswordAttempt.sh
    │   └── utils                  # Utility file. 
    │       └── utility.py
    └── rootEsc.py                  
```
## Language used 
- Python
- Bash
  
## Installation
Clone the repository and make the script executable:
```bash
git clone https://github.com/PkTheHacker10/rootEsc.git
cd rootEsc/rootEsc
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
This tool is intended for security research ,educational purposes only ,to understand the privilege escalation vectors and how the standard tool like linpeas ,winpeas is working not for **Reinventing the wheel**.  

## License
MIT License. See `LICENSE` for details.

