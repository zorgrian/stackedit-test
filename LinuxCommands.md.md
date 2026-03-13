# Useful Linux Commands

---

# System Information

```
uname -a
```
Show kernel and system information.

```
hostnamectl
```
Detailed system information including OS and architecture.

```
uptime
```
System uptime and load averages.

```
lscpu
```
CPU architecture and capabilities.

```
lsblk
```
List block devices.

```
lsblk -f
```
Block devices with filesystem information.

```
lsblk -o NAME,FSTYPE,SIZE,MOUNTPOINT,UUID
```
Detailed drive listing.

```
df -h
```
Disk usage.

```
free -h
```
Memory usage.

```
du -sh *
```
Directory sizes in current directory.

---

# Files and Directories

```
ls -lah
```
Detailed directory listing.

```
tree
```
Display directory tree.

```
cp source dest
```
Copy file.

```
cp -r dir1 dir2
```
Copy directory recursively.

```
mv old new
```
Move or rename file.

```
rm file
```
Delete file.

```
rm -r directory
```
Delete directory.

```
mkdir name
```
Create directory.

```
mkdir -p path/to/dir
```
Create nested directories.

***

# File Searching

```
find . -name "filename"
```
Find file by name.

```
find . -type f -size +100M
```
Find files larger than 100MB.

```
locate filename
```
Fast indexed search.

```
which program
```
Show program location.

***

# Text Processing

```
cat file
```
Display file.

```
less file
```
Scrollable viewer.

```
head file
```
First lines.

```
tail file
```
Last lines.

```
tail -f logfile
```
Follow a log file live.

```
grep "text" file
```
Search text.

```
grep -r "text" directory
```
Recursive search.

```
wc -l file
```
Count lines.

---

# Permissions

```
chmod +x script.sh
```
Make file executable.

```
chmod 644 file
```
Set permissions.

```
chown user:group file
```
Change ownership.

---

# Disk and File systems

```
mount
```
Show mounted file systems.

```
mount -a
```
Mount everything in `/etc/fstab`.

```
blkid
```
Show filesystem UUIDs.

***

# Networking

```
ip a
```
Show network interfaces.

```
ip r
```
Routing table.

```
ping host
```
Test connectivity.

```
ss -tuln
```
Show listening ports.

```
curl ifconfig.me
```
Show public IP.

***

# Processes

```
ps aux
```
List processes.

```
top
```
Process monitor.

```
htop
```
Interactive process monitor.

```
kill PID
```
Terminate process.

```
kill -9 PID
```
Force terminates process.

***

# Package Management (Debian / Ubuntu)

```
sudo apt update
```

```
sudo apt upgrade
```

```
sudo apt install package
```

```
sudo apt remove package
```

***

# System Logs

```
journalctl
```
System logs.

```
journalctl -xe
```
Recent errors.

```bash
journalctl -u service
```
Logs for a service.

***

# systemctl

```bash
systemctl status service
```

```bash
systemctl start service
```

```bash
systemctl stop service
```

***

# File Transfer

## rsync

Efficient file synchronisation.

```bash
rsync -av source/ destination/
```

```bash
rsync -av source/ user@host:/path/
```

```bash
rsync -av user@host:/path/ destination/
```

```bash
rsync -av --progress source/ destination/
```

```bash
rsync -av --delete source/ destination/
```

```
rsync -avz user@host:/path/ destination/
```

***

## `scp`

Secure copy over SSH.

```bash
scp file user@host:/path/
```

```bash
scp user@host:/path/file .
```

```bash
scp -r directory user@host:/path/
```

```bash
scp file user@host:/path/newname
```

---

# `ssh`

Remote login.

```bash
ssh user@host
```

```bash
ssh user@host "command"
```

```bash
ssh -X user@host
```

```bash
ssh -p 2222 user@host
```

***

# Terminal Power Tools

## watch

Run a command repeatedly.

```bash
watch command
```

Example:

```
watch -n 2 df -h
```

***

## xargs

Build command arguments from input.

```bash
find . -name "*.log" | xargs rm
```

***

## tee

Write output to both screen and file.

```bash
command | tee file.txt
```

***

## column

Format output into columns.

```
cat file | column -t
```

***

## `lsof`

List open files.

```
lsof
```

```bash
lsof -i :80
```

***

## `nc (netcat)`

Network debugging tool.

```bash
nc host port
```

Example:

```bash
nc localhost 80
```

***

## `strace`

Trace system calls.

```bash
strace program
```

---

## watch differences

```bash
watch -d command
```

Highlight changing output.

## The quick terminal method (very fast)

```bash
sudo du -xh / --max-depth=1 2>/dev/null | sort -h
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYyOTA3ODc2NCw5NDk0MTE4OF19
-->