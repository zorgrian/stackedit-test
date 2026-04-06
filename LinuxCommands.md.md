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

Delete directory recursively.

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

Find files larger than 100 MB.

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

***

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

***

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

***

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

***

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

***

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

***

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
### How to use `rsync` to transfer directories from one Linux machine to another

`rsync` is a powerful tool for transferring files and directories between Linux machines. It is efficient, fast, and can handle large amounts of data. Here’s how you can use `rsync` to transfer directories from one Linux machine to another:

1. Open a terminal on the source machine (the machine where the directory is located).
2. Use the following command to transfer the directory to the destination machine:

```bash
rsync -avz /path/to/source/directory/ user@destination_machine:/path/to/destination/directory/
```

Replace `/path/to/source/directory/` with the actual path of the directory you want to transfer, `user` with your username on the destination machine, `destination_machine` with the IP address or `hostname` of the destination machine, and `/path/to/destination/directory/` with the desired path on the destination machine.
3. Press Enter to execute the command. `rsync` will start transferring the files and directories from the source machine to the destination machine. The `-avz` options stand for:
* `-a`: Archive mode; it preserves symbolic links, permissions, timestamps, and other file attributes.
* `-v`: Verbose mode; it provides detailed output of the transfer process.
* `-z`: Compress file data during the transfer, which can speed up the transfer if the files are large.
4. Once the transfer is complete, you can verify that the files have been successfully transferred by logging into the destination machine and checking the destination directory.    

Note: Make sure that you have SSH access to the destination machine and that `rsync` is installed on both machines. You may also need to configure your firewall settings to allow the transfer.

## Examples

* To transfer a directory named `my_folder` from the source machine to the destination machine:

```bash
rsync -avz /home/user/my_folder/ user@destination_machine:/home/user/destination_folder/
```
* To transfer a directory while excluding certain files (e.g., `*.log` files):

```bash
rsync -avz --exclude='*.log' /home/user/my_folder/ user@destination_machine:/home/user/destination_folder/
```

* To transfer a directory and delete files in the destination that are not present in the source:

```bash
rsync -avz --delete /home/user/my_folder/ user@destination_machine:/home/user/destination_folder/
```

By following these steps, you can easily transfer directories between Linux machines using `rsync`.

## How to find the IP address of a Linux machine

To find the IP address of a Linux machine, you can use the following command in the terminal:

```bash
ip addr show
```
This command will display the network interfaces and their associated IP addresses. Look for the interface that is connected to the network (e.g., `eth0`, `wlan0`, etc.) and find the `inet` entry, which will show the IP address.

On some systems, you can also use the `ifconfig` command:

```bash
ifconfig
```
This command will also display the network interfaces and their IP addresses. Again, look for the relevant interface and find the `inet` entry to see the IP address.

On a Chromebook, you can find the IP address by clicking on the network icon in the system tray, selecting the connected network, and looking for the IP address in the network details. Or, on crostini, you can use the `ip addr show` command in the terminal to find the IP address.


This is ostrich-powered content. For more information, visit [ostrich-powered.com](https://ostrich-powered.com).




***

## `scp`

Secure copy over SSH. 

**Note:**
* This will do a similar job to `rsync`, but doesn't show the rate of transfer.
* It's simpler and can be used without hassle

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

***

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

***

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

```bash
cat file | column -t
```

***

## `lsof`

List open files.

```bash
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

**Note:** The mdBook folder can be replaced with any folder name

Example: we want to zip 	`MACROVEND`, and this is a folder.

```bash
zip -r macrovend-backup-$(date +%Y-%m-%d).zip MACROVEND
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
eyJoaXN0b3J5IjpbMTcwMDY3NDc1NSwxNzE4MDIwMjM3LDIwNT
U1MzI4NTMsMTQ4OTE2NjE0LDMyODQyNzUwOSwxMTk1MTkyODI1
LDE4MDc2MzE2MjcsLTE2NzU4NjM2NjksNzE4NTk1ODc4LDM0Nj
E1MzYyMiwxOTk4ODAzMDgwLC0yMDYxNDMyNzUyLDk0OTQxMTg4
XX0=
-->