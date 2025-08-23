# Linux Administration Labs 🐧

This repo contains hands-on labs for core Linux administration tasks.  
Covers user management, permissions, services, firewalls, storage, and scheduling.  

## Topics Covered
- User & group management
- File permissions (SUID, SGID, Sticky Bit)
- ACLs and sudo
- SELinux
- NFS, Samba, FTP
- DNS, DHCP, NTP
- iptables, firewalld
- LVM and partitions
- Cron and at jobs

## Lab Structure
Each lab has:
1. Problem statement
2. Steps followed
3. Configuration files
4. Verification commands
5. Screenshots (optional)

## Example
### Lab: NFS Setup
- Setup 1 NFS server and 1 client VM
- Export `/mnt/share` with read-write permissions
- Mount NFS on client at `/mnt/nfs`
