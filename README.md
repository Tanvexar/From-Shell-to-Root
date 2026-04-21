# 🔥 Red Team Notes (Pentesting)

This repository contains real-world penetration testing techniques, reverse shells, and privilege escalation methods.

---

## 📂 Sections

### 🔐 Privilege Escalation

* Sudo Misconfiguration Exploitation
* Writable Script Abuse

### 🧨 Reverse Shells

* Netcat FIFO Reverse Shell
* Bash Reverse Shell
* Python Reverse Shell

---

## 🧠 Methodology

1. Enumeration (`sudo -l`, file permissions)
2. Identify misconfigurations
3. Exploit using reverse shell
4. Gain elevated access

---

## 🚀 Example Attack Flow

* Found sudo permission:

  ```
  (ALL) NOPASSWD: /usr/bin/perl /home/itguy/backup.pl
  ```
* Script executed external file
* Modified file with reverse shell
* Got root shell

---

## 🎯 Goal

To document practical learning and help others understand real attack paths.

---

## ⚠️ Disclaimer

For educational and ethical hacking purposes only.
