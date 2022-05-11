# Samba
Basically Samba its a open-source file-share service

# commands
- testparm: will test the sintax of the samba server
- smbpasswd -a <username>: create a user
- smbpasswd -e <username>: enable a user

# [global]
- interfaces = <interfaces>

# Users
- read only: yes|no 
- browseable: yes|no 
- writeable: yes|no
- valid users: @group user 
- guest ok: yes|no 

# smbclient
```sh
smbclient //samba.example.com/directory/ - U <user>
```

