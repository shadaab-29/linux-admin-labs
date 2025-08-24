# 🐧 Linux User & Group Management Cheat Sheet

## 🔹 Quick Reference Table

| Command | Description |
|---------|-------------|
| `useradd username` | Create a new user |
| `passwd username` | Set/change user password |
| `usermod -aG group user` | Add user to a secondary group |
| `usermod -g group user` | Change user’s primary group |
| `usermod -d /path user` | Change home directory |
| `usermod -s /bin/shell user` | Change login shell |
| `userdel username` | Delete user (keep home dir) |
| `userdel -r username` | Delete user + home dir |
| `groupadd groupname` | Create a group |
| `groupdel groupname` | Delete a group |
| `groupmod -n new old` | Rename group |
| `id username` | Show UID, GID, groups |
| `groups username` | Show group memberships |
| `gpasswd -a user group` | Add user to group |
| `gpasswd -d user group` | Remove user from group |
| `gpasswd -A user group` | Set group admin |
| `gpasswd -M "u1,u2"` | Set multiple group members |
| `whoami` | Show current logged-in user |
| `su - user` | Switch user |
| `usermod -aG sudo user` | Add user to sudo (Debian/Ubuntu) |
| `usermod -aG wheel user` | Add user to sudo (RHEL/CentOS) |

---

## 🔹 User Management
- **Add user**
useradd username
useradd -m -s /bin/bash alice # with home dir & shell

markdown
Copy
Edit

- **Set/Change password**
passwd username

markdown
Copy
Edit

- **Modify user**
usermod -s /bin/zsh alice # change shell
usermod -d /new/home alice # change home dir
usermod -aG developers alice # add to secondary group

markdown
Copy
Edit

- **Delete user**
userdel username
userdel -r username # also remove home dir

markdown
Copy
Edit

- **Switch user**
su - username

sql
Copy
Edit

- **Check current user**
whoami

yaml
Copy
Edit

---

## 🔹 Group Management
- **Add group**
groupadd developers

markdown
Copy
Edit

- **Delete group**
groupdel developers

markdown
Copy
Edit

- **Modify group**
groupmod -n newgroup oldgroup

yaml
Copy
Edit

---

## 🔹 Membership & Info
- **User info**
id alice

markdown
Copy
Edit

- **Groups of a user**
groups alice

markdown
Copy
Edit

- **Change primary group**
usermod -g developers alice

pgsql
Copy
Edit

- **Add to secondary group**
usermod -aG docker alice

yaml
Copy
Edit

---

## 🔹 `gpasswd` – Group Administration
- **Set/change group password**
gpasswd developers

pgsql
Copy
Edit

- **Add user to group**
gpasswd -a alice developers

sql
Copy
Edit

- **Remove user from group**
gpasswd -d alice developers

markdown
Copy
Edit

- **Assign group admin**
gpasswd -A bob developers

markdown
Copy
Edit

- **Set group members**
gpasswd -M "alice,bob" developers

yaml
Copy
Edit

---

## 🔹 Files & Configs
- `/etc/passwd` → user accounts  
- `/etc/shadow` → passwords (hashed)  
- `/etc/group` → groups  
- `/etc/sudoers` → sudo rules (edit via `visudo`)  

---

## 🔹 Sudo Permissions
- Add user to sudoers:
usermod -aG sudo alice # Debian/Ubuntu
usermod -aG wheel alice # RHEL/CentOS

Copy
Edit
