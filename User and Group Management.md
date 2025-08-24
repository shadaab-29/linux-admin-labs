# 🐧 Linux User & Group Management Cheat Sheet

## 🔹 Quick Reference Table

| Command | Description | Example |
|---------|-------------|---------|
| `useradd username` | Create a new user | `useradd alice` |
| `passwd username` | Set/change user password | `passwd alice` |
| `usermod -aG group user` | Add user to a secondary group | `usermod -aG docker alice` |
| `usermod -g group user` | Change user’s primary group | `usermod -g developers alice` |
| `usermod -d /path user` | Change home directory | `usermod -d /home/newalice alice` |
| `usermod -s /bin/shell user` | Change login shell | `usermod -s /bin/zsh alice` |
| `userdel username` | Delete user (keep home dir) | `userdel alice` |
| `userdel -r username` | Delete user + home dir | `userdel -r alice` |
| `groupadd groupname` | Create a group | `groupadd developers` |
| `groupdel groupname` | Delete a group | `groupdel developers` |
| `groupmod -n new old` | Rename group | `groupmod -n dev developers` |
| `id username` | Show UID, GID, groups | `id alice` |
| `groups username` | Show group memberships | `groups alice` |
| `gpasswd -a user group` | Add user to group | `gpasswd -a alice developers` |
| `gpasswd -d user group` | Remove user from group | `gpasswd -d alice developers` |
| `gpasswd -A user group` | Set group admin | `gpasswd -A bob developers` |
| `gpasswd -M "u1,u2"` | Set multiple group members | `gpasswd -M "alice,bob" developers` |
| `whoami` | Show current logged-in user | `whoami` |
| `su - user` | Switch user | `su - alice` |
| `usermod -aG sudo user` | Add user to sudo (Debian/Ubuntu) | `usermod -aG sudo alice` |
| `usermod -aG wheel user` | Add user to sudo (RHEL/CentOS) | `usermod -aG wheel alice` |

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
