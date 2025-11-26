Users & Permissions — Linux Notes
1. Understanding Users in Linux

Linux is a multi-user operating system. This means multiple users can exist on the same system, each with their own permissions and environment.

Types of Users

Root user

The administrator of the system.

Has full control over all files and commands.

Username: root

UID: 0

Regular user

Created for daily use.

Limited permissions.

UID range usually starts from 1000.

System users

Used by services (e.g., www-data, mysql).

Not meant for login.

Important Files

/etc/passwd → Stores user account information

/etc/shadow → Stores encrypted passwords

/etc/group → Stores group information

2. Creating & Managing Users
Create a user
sudo useradd username

Create a user with a home directory
sudo useradd -m username

Set user password
sudo passwd username

Delete a user
sudo userdel username

Delete user + home directory
sudo userdel -r username

3. Groups in Linux
Create a group
sudo groupadd groupname

Add a user to a group
sudo usermod -aG groupname username

Check groups of a user
groups username

4. File Permissions in Linux

Every file and directory has:

Owner

Group

Other (everyone else)

Each can have three types of permissions:

r → read

w → write

x → execute

Permission Structure

Example output from ls -l:

-rwxr-xr--


Breakdown:

- → file type

rwx → owner permissions

r-x → group permissions

r-- → others permissions

5. Changing Permissions
Change owner of a file
sudo chown user file

Change owner and group
sudo chown user:group file

Change group only
sudo chgrp group file

6. Changing Permission Modes
Symbolic method
chmod u+x file     # add execute to user
chmod g-w file     # remove write from group
chmod o+r file     # add read to others

Numeric (octal) method
Permission	Value
r	4
w	2
x	1

Examples:

chmod 755 file   # rwx r-x r-x
chmod 644 file   # rw- r-- r--
chmod 700 file   # rwx --- ---

7. Special Permissions
SetUID (4xxx)

File runs with the permissions of the file owner.
Example:

chmod 4755 file

SetGID (2xxx)

File runs with group permissions, or directory inherits group.

chmod 2755 dir

Sticky Bit (1xxx)

Only the file owner can delete files inside a directory.
Used in /tmp:

chmod 1777 /dir

8. Checking Permissions
List detailed permissions
ls -l

Check ACLs
getfacl file

9. Access Control Lists (ACLs)

ACLs allow more granular permissions.

Set ACL
setfacl -m u:username:rwx file

Remove ACL
setfacl -x u:username file

Default ACL on a directory
setfacl -m d:u:username:rwx directory

10. Switch Users
Switch to another user
su username

Switch to root
sudo su

11. View Current User
whoami

12. Summary

Linux users and groups manage access and improve security.

Permissions define who can read, write, or execute files.

chmod, chown, and usermod are essential daily commands.

ACLs provide advanced control beyond traditional permissions.
