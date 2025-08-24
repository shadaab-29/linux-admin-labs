# 🐧 Linux User & Group Management Cheat Sheet

## 🔹 User Management
- **Add user**
  ```bash
  useradd username
  useradd -m -s /bin/bash alice   # with home dir & shell
Set/Change password

bash
Copy
Edit
passwd username
Modify user

bash
Copy
Edit
usermod -s /bin/zsh alice       # change shell
usermod -d /new/home alice      # change home dir
usermod -aG developers alice    # add to secondary group
Delete user

bash
Copy
Edit
userdel username
userdel -r username             # also remove home dir
Switch user

bash
Copy
Edit
su - username
Check current user

bash
Copy
Edit
whoami
🔹 Group Management
Add group

bash
Copy
Edit
groupadd developers
Delete group

bash
Copy
Edit
groupdel developers
Modify group

bash
Copy
Edit
groupmod -n newgroup oldgroup
🔹 Membership & Info
User info

bash
Copy
Edit
id alice
Groups of a user

bash
Copy
Edit
groups alice
Change primary group

bash
Copy
Edit
usermod -g developers alice
Add to secondary group

bash
Copy
Edit
usermod -aG docker alice
🔹 gpasswd – Group Administration
Set/change group password

bash
Copy
Edit
gpasswd developers
Add user to group

bash
Copy
Edit
gpasswd -a alice developers
Remove user from group

bash
Copy
Edit
gpasswd -d alice developers
Assign group admin

bash
Copy
Edit
gpasswd -A bob developers
Set group members

bash
Copy
Edit
gpasswd -M "alice,bob" developers
🔹 Files & Configs
/etc/passwd → user accounts

/etc/shadow → passwords (hashed)

/etc/group → groups

/etc/sudoers → sudo rules (edit via visudo)

🔹 Sudo Permissions
Add user to sudoers:

bash
Copy
Edit
usermod -aG sudo alice      # Debian/Ubuntu
usermod -aG wheel alice     # RHEL/CentOS