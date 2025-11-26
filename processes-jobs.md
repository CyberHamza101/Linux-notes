# Linux Processes & Jobs Management

## 1. What Is a Process?
A process is a running program in memory. Each process has:
- PID (Process ID)
- PPID (Parent Process ID)
- User
- State
- Memory/CPU usage

## 2. View Running Processes

### ps
```bash
ps
ps aux
ps aux | grep nginx
```

### top
```bash
top
```

### htop
```bash
htop
```

## 3. Process Details

### pidof
```bash
pidof firefox
```

### pgrep
```bash
pgrep ssh
```

## 4. Kill / Manage Processes

### kill
```bash
kill <PID>
kill -9 <PID>
kill -l
```

## 5. Background & Foreground Jobs

### Run in background
```bash
command &
```

### List jobs
```bash
jobs
```

### Stop job
Press CTRL+Z

### Resume in foreground
```bash
fg %1
```

### Resume in background
```bash
bg %1
```

## 6. nohup (Run after logout)
```bash
nohup command &
```

## 7. systemctl (Service Management)
```bash
sudo systemctl start ssh
sudo systemctl stop ssh
sudo systemctl restart ssh
sudo systemctl status ssh
```

## 8. Nice & Renice (Priority)
```bash
nice -n 10 command
sudo renice -n 5 -p <PID>
```

## 9. Logs
```bash
tail -f /var/log/syslog
tail -f /var/log/auth.log
```

