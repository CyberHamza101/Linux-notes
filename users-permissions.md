
# Users & Permissions

# Linux Users, Groups & Permissions — Essential Commands

## 📍 Overview

Linux is a multi-user operating system. Understanding users, groups, and permissions is critical for cybersecurity, SOC analysis, and penetration testing.
These commands and concepts help you manage access, secure files, and control system resources.

---

## 👤 Users in Linux

### Types of Users

**Root User**

* System administrator
* Full control over all files and commands
* Username: `root`
* UID: `0`

**Regular User**

* Created for daily tasks
* Limited permissions
* UID usually starts from `1000`

**System Users**

* Used by services (e.g., `www-data`, `mysql`)
* Not meant for login

### Important Files

| File          | Purpose                    |
| ------------- | -------------------------- |
| `/etc/passwd` | Stores user account info   |
| `/etc/shadow` | Stores encrypted passwords |
| `/etc/group`  | Stores group info          |

---

## 🛠️ Creating & Managing Users

### Create a User

```bash
sudo useradd username
```

### Create a User with Home Directory

```bash
sudo useradd -m username
```

### Set User Password

```bash
sudo passwd username
```

### Delete a User

```bash
sudo userdel username
```

### Delete User + Home Directory

```bash
sudo userdel -r username
```

---

## 👥 Groups in Linux

### Create a Group

```bash
sudo groupadd groupname
```

### Add a User to a Group

```bash
sudo usermod -aG groupname username
```

### Check Groups of a User

```bash
groups username
```

---

## 🔓 File Permissions in Linux

Each file and directory has:

* **Owner**
* **Group**
* **Other** (everyone else)

### Permission Types

| Symbol | Meaning |
| ------ | ------- |
| r      | Read    |
| w      | Write   |
| x      | Execute |

### Example Output from `ls -l`

```text
-rwxr-xr--
```

**Breakdown:**

* `-` → File type
* `rwx` → Owner permissions
* `r-x` → Group permissions
* `r--` → Others permissions

---

## 🛠️ Changing Ownership & Permissions

### Change Owner

```bash
sudo chown user file
```

### Change Owner & Group

```bash
sudo chown user:group file
```

### Change Group Only

```bash
sudo chgrp group file
```

### Change Permission Modes

**Symbolic Method**

```bash
chmod u+x file   # add execute to user
chmod g-w file   # remove write from group
chmod o+r file   # add read to others
```

**Numeric (Octal) Method**

| Permission | Value |
| ---------- | ----- |
| r          | 4     |
| w          | 2     |
| x          | 1     |

```bash
chmod 755 file   # rwx r-x r-x
chmod 644 file   # rw- r-- r--
chmod 700 file   # rwx --- ---
```

---

## ⚡ Special Permissions

**SetUID (4xxx)**

* File runs with owner permissions

```bash
chmod 4755 file
```

**SetGID (2xxx)**

* File/dir runs with group permissions

```bash
chmod 2755 dir
```

**Sticky Bit (1xxx)**

* Only file owner can delete files inside a directory
* Commonly used in `/tmp`

```bash
chmod 1777 /dir
```

---

## 🔍 Checking Permissions

### List Detailed Permissions

```bash
ls -l
```

### Check ACLs (Access Control Lists)

```bash
getfacl file
```

---

## 📓 Access Control Lists (ACLs)

### Set ACL

```bash
setfacl -m u:username:rwx file
```

### Remove ACL

```bash
setfacl -x u:username file
```

### Default ACL on a Directory

```bash
setfacl -m d:u:username:rwx directory
```

---

## 🔄 Switching Users

### Switch to Another User

```bash
su username
```

### Switch to Root

```bash
sudo su
```

### View Current User

```bash
whoami
```

---

## 🎯 Summary

* Linux users and groups manage system access.
* Permissions define who can read, write, or execute files.
* `chmod`, `chown`, and `usermod` are essential daily commands.
* ACLs provide advanced access control beyond standard permissions.
