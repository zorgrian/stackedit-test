# 🧱 Useful Linux Commands

**These are ostrich-powered 🪶**

***

## System Information

```
uname -a
```

Show kernel and system information.

```bash
hostnamectl
```

Detailed system information including OS and architecture.

```bash
uptime
```

System uptime and load averages.

```bash
lscpu
```

CPU architecture and capabilities.

```bash
lsblk
```

List block devices.

```bash
lsblk -f
```

Block devices with filesystem information.

```bash
lsblk -o NAME,FSTYPE,SIZE,MOUNTPOINT,UUID
```

Detailed drive listing.

```bash
df -h
```

Disk usage.

```bash
free -h
```

Memory usage.

```bash
du -sh *
```

Directory sizes in current directory.

***

## Files and Directories

```bash
ls -lah
```

Detailed directory listing.

```bash
tree
```

Display directory tree.

```bash
cp source dest
```

Copy file.

```bash
cp -r dir1 dir2
```

Copy directory recursively.

```bash
mv old new
```

Move or rename file.

```bash
rm file

```

Delete file.

```bash
rm -r directory

```

Delete directory.

```bash
mkdir name

```

Create directory.

```bash
mkdir -p path/to/dir

```

Create nested directories.

----------

## File Searching

```bash
find . -name "filename"

```

Find file by name.

```bash
find . -type f -size +100M

```

Find files larger than 100MB.

```bash
locate filename

```

Fast indexed search.

```bash
which program

```

Shows the program location.

----------

## Text Processing

```bash
cat file

```

Display file.

```bash
less file

```

Scrollable viewer.

```bash
head file

```

First lines.

```bash
tail file

```

Last lines.

```bash
tail -f logfile

```

Follow a log file live.

```bash
grep "text" file

```

Search text.

```bash
grep -r "text" directory

```

Recursive search.

```bash
wc -l file

```

Count lines.

----------

## Permissions

```bash
chmod +x script.sh

```

Make file executable.

```bash
chmod 644 file

```

Set permissions.

```bash
chown user:group file

```

Change ownership.

----------

## Disk and Filesystems

```bash
mount

```

Show mounted filesystems.

```bash
mount -a

```

Mount everything in `/etc/fstab`.

```bash
blkid

```

Show filesystem UUIDs.

----------

## Networking

```bash
ip a

```

Show network interfaces.

```bash
ip r

```

Routing table.

```bash
ping host

```

Test connectivity.

```bash
ss -tuln

```

Show listening ports.

```bash
curl ifconfig.me

```

Show public IP.

----------

## Processes

```bash
ps aux

```

List processes.

```bash
top

```

Process monitor.

```bash
htop

```

Interactive process monitor.

```bash
kill PID

```

Terminate process.

```bash
kill -9 PID

```

Force terminate-process.

----------

## Package Management (Debian / Ubuntu)

```bash
sudo apt update

```

```bash
sudo apt upgrade

```

```bash
sudo apt install package

```

```bash
sudo apt remove package

```

----------

## System Logs

```bash
journalctl

```

System logs.

```bash
journalctl -xe

```

Recent errors.

```bash
journalctl -u service

```

Logs for a service.

----------

## systemctl

```bash
systemctl status service

```

```bash
systemctl start service

```

```bash
systemctl stop service

```

----------

## File Transfer

### rsync

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

```bash
rsync -avz user@host:/path/ destination/

```

----------

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

----------

## ssh

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

----------

## Terminal Power Tools

### watch

Run a command repeatedly.

```bash
watch command

```

Example:

```bash
watch -n 2 df -h

```

----------

## xargs

Build command arguments from input.

```bash
find . -name "*.log" | xargs rm

```

----------

## tee

Write output to both screen and file.

```bash
command | tee file.txt

```

----------

## column

Format output into columns.

```bash
cat file | column -t

```

----------

## `lsof`

List open files.

```bash
lsof

```

```bash
lsof -i :80

```

----------

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

***

## watch differences

```bash
watch -d command
```

Highlight changing output.

----------

## Disk Space Investigation

Quick overview of filesystem usage.

```bash
sudo du -xh / --max-depth=1 2>/dev/null | sort -h
```

### Drill down into home directory

```bash
du -h --max-depth=1 /home/zorgrian | sort -h
```

### Find large files

```bash
find / -type f -size +500M 2>/dev/null
```

### Largest files and directories

```bash
sudo du -ah / | sort -rh | head -20
```

***

### GPU activity
```bash
sudo apt install nvtop
```
**Then to actually use this:**
```bash
nvtop
```
This is an astonishing command, as it shows the whole ostrich.

***
### How to zip an mdBook project — with a timestamp

```bash
zip -r mdbook-backup-$(date +%Y-%m-%d).zip . \
    -x "*.git*" -x "book/*"
```
## Why exclude these?

-   `.git` → huge, unnecessary
-   `book/` → generated output (rebuildable)

👉 This keeps your backup **clean and small**    
### 📦 Example result

```bash
mdbook-backup-2026-03-22.zip
```
### 🚀 Restore later
```bash
unzip mdbook-backup-2026-03-22.zip -d restore-folder
```
### A better version
```bash
zip -r /mnt/DATA/mdbook-backup-$(date +%Y-%m-%d-%H%M).zip \
    /mnt/DATA/YOOFAB-MKDOCS-8-mdbook \
    -x "/mnt/DATA/YOOFAB-MKDOCS-8-mdbook/.git/*" \
    -x "/mnt/DATA/YOOFAB-MKDOCS-8-mdbook/book/*" \
    -x "*.zip"
```

### Note:

**This document can be extended over time as additional useful commands are discovered.**
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQzNDQxMDA3NiwxMTk1MTkyODI1LDE4MD
c2MzE2MjcsLTE2NzU4NjM2NjksNzE4NTk1ODc4LDM0NjE1MzYy
MiwxOTk4ODAzMDgwLC0yMDYxNDMyNzUyLDk0OTQxMTg4XX0=
-->