# ⚙️ Linux Process Management

A **process** is simply a running instance of a program.

Example:
- You run `vim` → a process is created
- You run `nginx` → a process is created

---

# 🧠 1. What is a Process?

- Every command you run = process
- Each process has:
  - PID (Process ID)
  - PPID (Parent Process ID)
  - State (running, sleeping, etc.)

---

# 🔄 2. Process Lifecycle

1. Created (fork)
2. Running
3. Waiting / Sleeping
4. Terminated

---

# 🧾 3. View Processes

## Basic
ps

## Detailed
ps -ef

## Real-time monitoring
top

## Better top
htop

---

# 🔍 4. Important Fields

ps -ef output:

UID   PID   PPID   CMD

- PID → unique process ID
- PPID → parent process
- CMD → command

---

# ⚔️ 5. Kill Processes

## Graceful stop
kill PID

## Force kill
kill -9 PID

## Kill by name
pkill nginx

---

# ⚡ 6. Process Priority

## View priority
top

## Change priority
nice -n 10 command
renice 5 -p PID

---

# 🧵 7. Foreground vs Background Process

## Foreground
- Runs in terminal
- Blocks terminal

Example:
sleep 100

---

## Background
- Runs in background
- Terminal free

Example:
sleep 100 &

---

## Move between states

Ctrl + Z  → stop process  
bg        → run in background  
fg        → bring to foreground  

---

# 🤖 8. What is a Daemon?

A **daemon** is a background process that runs continuously.

Examples:
- sshd
- httpd
- crond

👉 Key difference:
- Process → any running program  
- Daemon → background service (usually system-related)

---

# 🏢 9. System Processes

- Started by system (PID 1 = systemd)
- Run in background
- Provide system services

Examples:
- systemd
- udevd
- journald

---

# 🔥 10. systemd & systemctl

Modern Linux uses **systemd** to manage services.

---

# 📦 11. Service vs Socket Units

## .service
- Actual service (nginx, sshd)

## .socket
- Socket-based activation
- Service starts only when request comes

Example:
sshd.socket → starts sshd.service on demand

---

# 🛠️ 12. Basic systemctl Commands

## Start service (temporary)
systemctl start nginx

## Stop service
systemctl stop nginx

## Restart
systemctl restart nginx

## Status
systemctl status nginx

---

# 🔁 13. Enable vs Start (IMPORTANT)

## start
- Starts service NOW
- Does NOT persist after reboot

## enable
- Starts service at BOOT
- Does NOT start immediately

---

## 🔥 Enable + Start together

systemctl enable --now nginx

---

# ❌ 14. Disable vs Stop

## stop
- Stops service now

## disable
- Prevents service from starting at boot

---

# 🚫 15. Masking Services

Mask = completely block service

systemctl mask nginx

- Cannot be started manually or automatically

## Unmask
systemctl unmask nginx

---

# 🔍 16. Check Enabled Services

systemctl list-unit-files | grep enabled

---

# 📊 17. Check Running Services

systemctl list-units --type=service

---

# 📂 18. Where Services Live

- /usr/lib/systemd/system/  → default
- /etc/systemd/system/      → custom

---

# ⚡ 19. Logs (VERY IMPORTANT)

## View logs
journalctl

## Logs for service
journalctl -u nginx

## Live logs
journalctl -f

