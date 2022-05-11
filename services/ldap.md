# LDAP Definition

### LDAP Installation
```
apt-get install slapd ldap-utils -y
```

### LDAP Commands
- dpkg-reconfigure slapd
- slapcat:
- ldapsearch -x:

### Creating new Entries
```
vim base.ldif
> dn: ou=your_ou, dc=yourdomain,dc=com
> objectClass: organizationalUnit
> ou:your_ou

ldapadd -x -D cn=admin,dcyourdomain,dc=com -W -f base.ldif
```

### Creating a User
```
vim ldapuser.ldif
>dn: uid=user1,ou=email,dc=local,dc-info
objectClass: posixAccount
objectClass: inetOrgPerson
objectClass: shadowAccount
cn: user1
uidNumber: x
gidNumber: x
loginShell: /bin/bash
homeDirectory: /home/user1
userPassword: {SSHA}xxxxxx
sn:debian

dn: cn=user1,ou=email,dc=info,dc=local
objectClass: posixGroup
cn: user1
gidNumber: x
memberUid: user1

```

### Creating a Group
```
vim groups.ldif
>dn: group=email,dc=info,dc=local
objectClass: posixGroup
group: email

```

### Automatic home dir on login
```
vim /etc/pam.d/login
> session required pam_mkhomedir.so skel=/etc/skel umask=0077
> :wq
```
