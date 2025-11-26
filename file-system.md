# File System & Navigation
# Linux File System -- Essential Commands

## 📌 Overview

Understanding Linux file system navigation is essential for
cybersecurity, SOC analysis, and penetration testing.\
These commands help you move, search, read, and modify files
efficiently.

------------------------------------------------------------------------

## 📁 Navigation Commands

### `pwd` -- Print Working Directory

Shows your current location.

``` bash
pwd
```

### `ls` -- List Directory Contents

``` bash
ls          # list files
ls -l       # long format
ls -a       # show hidden files
ls -lh      # human-readable sizes
```

### `cd` -- Change Directory

``` bash
cd /etc
cd ~/Documents
cd ..        # go up one level
cd -         # go back to previous directory
```

------------------------------------------------------------------------

## 📂 File & Directory Management

### `mkdir` -- Create Directory

``` bash
mkdir test
mkdir -p a/b/c   # create nested folders
```

### `rmdir` -- Remove Empty Directory

``` bash
rmdir test
```

### `rm` -- Remove Files & Folders

``` bash
rm file.txt
rm -r folder        # delete directory and contents
rm -rf folder       # force delete (Dangerous!)
```

### `touch` -- Create Empty File

``` bash
touch notes.txt
```

### `cp` -- Copy Files & Folders

``` bash
cp file.txt backup.txt
cp -r folder/ backup/
```

### `mv` -- Move or Rename

``` bash
mv file.txt /tmp/
mv oldname.txt newname.txt
```

------------------------------------------------------------------------

## 📄 Viewing & Reading Files

### `cat` -- Print File Content

``` bash
cat file.txt
```

### `tac` -- Reverse cat (bottom → top)

``` bash
tac file.txt
```

### `less` -- Scroll Inside File

``` bash
less /var/log/syslog
```

### `head` & `tail`

``` bash
head file.txt        # show first 10 lines
tail file.txt        # last 10 lines
tail -f logfile      # watch log in real time
```

------------------------------------------------------------------------

## 🔍 Searching Files & Text

### `find` -- Search for Files

``` bash
find / -name passwd
find . -type f -size +10M
```

### `grep` -- Search Inside Files

``` bash
grep "root" /etc/passwd
grep -i "error" logfile
grep -R "password" /etc
```

------------------------------------------------------------------------

## 🔐 Permissions & Ownership

### `chmod` -- Change Permissions

``` bash
chmod 755 script.sh
chmod u+rwx,g+rx,o+rx file
```

### `chown` -- Change Ownership

``` bash
chown user:group file
```

------------------------------------------------------------------------

## 📦 Disk & Storage Commands

### `df` -- Disk Space

``` bash
df -h
```

### `du` -- Folder Size

``` bash
du -h folder/
du -h --max-depth=1
```

------------------------------------------------------------------------

## 🔗 Links

### Hard Link

``` bash
ln file.txt linkfile
```

### Symbolic Link

``` bash
ln -s /var/log/syslog loglink
```

------------------------------------------------------------------------

## 📝 Editing Files

### `nano`

``` bash
nano file.txt
```

### `vim`

``` bash
vim file.txt
```

------------------------------------------------------------------------

## ⚠️ Important Notes

-   Avoid `rm -rf /` (this wipes the system).
-   Prefer `less` over `cat` for big files.
-   Use `grep` + `tail -f` together to monitor logs.

------------------------------------------------------------------------

## 🛠 Practical Examples

### Find suspicious files bigger than 20MB:

``` bash
find /home -type f -size +20M
```

### Monitor authentication logs:

``` bash
tail -f /var/log/auth.log
```

### Search for "failed login" in logs:

``` bash
grep -i "failed" /var/log/auth.log
```

------------------------------------------------------------------------

## 🎯 Skills Gained

-   Navigating Linux efficiently\
-   Managing files & permissions\
-   Investigating logs\
-   Preparing for SOC Level 1 

