<h1 align="center">RootESC</h1>

<p align="center">
  A Linux privilege escalation analysis tool designed to identify potential attack vectors in system environments.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Language-Python-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Scripting-Bash-green?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Focus-Privilege%20Escalation-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Platform-Linux-yellow?style=for-the-badge" />
</p>

---

## 📌 Overview

**RootESC** is a security analysis tool created by **Pevinkumar A** to enumerate and detect possible privilege escalation vectors in Linux systems.

It helps security researchers understand:
- Misconfigurations
- Weak permissions
- Privilege escalation paths

---

## ✨ Features

### 🧑‍💻 System Enumeration
- User & group listing
- OS & kernel information
- System architecture detection

### 🔐 Privilege Analysis
- Sudo privileges inspection
- SUID & SGID binary detection
- Linux capabilities enumeration

### 📁 File System Analysis
- Writable files & directories detection
- Cron job analysis for root-level tasks

### ⚙️ Process Inspection
- Root-owned process detection
- Suspicious process location checks
- High CPU process monitoring

### 🌐 Network & Logs
- Unusual network connection detection
- Failed login attempt analysis

---

## 📂 Tool Structure

```

rootEsc/
├── modules/
│   ├── cli/
│   ├── core.py
│   ├── scripts/
│   │   ├── 1_system/
│   │   ├── 2_files/
│   │   ├── 3_process/
│   │   ├── 4_network/
│   │   └── 5_log/
│   └── utils/
└── rootEsc.py

````

---

## ⚙️ Installation

### 📥 Clone Repository
```bash id="q3p5vo"
git clone https://github.com/PkTheHacker10/rootEsc.git
cd rootEsc/rootEsc
````

---

## 🚀 Usage

### ▶️ Run Tool

```bash id="zq9d8k"
python3 rootEsc.py
```

### 📖 Help Menu

```bash id="1k3v2a"
python3 rootEsc.py -h
```

---

## 📊 Output

RootESC generates a structured security report including:

* System information
* User privileges
* Writable targets
* Running processes
* Privilege escalation vectors

---

## 🧪 Example Output

```bash id="x8v1lm"
[ ✓ ] Enumerating Id :
uid=1000(user1) gid=1000(users) groups=1000(users),4(adm),27(sudo)

[ ✓ ] Enumerating Uname :
Linux user1 6.8.0-51-generic x86_64 GNU/Linux

[ ✓ ] Enumerating SudoVersion :
Sudo version 1.9.15p5
Sudoers policy plugin version 1.9.15p5
```

---

## ⚠️ Disclaimer

This tool is intended for:

* Educational purposes
* Security research
* Understanding privilege escalation techniques

It is **not intended for unauthorized system access** or misuse.

---

## 📜 License

MIT License © PevinKumar A
