# Users and Groups
On Linux we have 5 most common commands to create, delete and manage users, which is(useradd, userdel, groupadd, groupdel and usermod)
---
### Useradd
basic structure: useradd -OPTIONS USERNAME

- Options:
	- d: Specify the home of the user (useradd -d /home/username USERNAME)
	- m: Create a new home (useradd -m /home/username USERNAME) 
	- s: Specify the shell of the user (useradd -s /bin/bash/) 

**Full command example**
```bash
useradd -m -d /home/username -s /bin/bash/ USERNAME
```
---
### Userdel
basic structure: userdel -OPTIONS USERNAME

- Options:
	- f: force the delete action
	- r: remove the home dir of the user

**Full command example**
```bash
userdel -rf USERNAME
```
---
### Groupadd
basic structure: groupadd -OPTIONS USERNAME

- Options:
	
**Full example command**
```bash
groupadd GROUPNAME
```
---
### Groupdel
basic structure: groupdel -OPTIONS GROUP


- Options:
	-f: delete the group even if he is the primary group of a user

**Full example command**
```bash
groupdel -f GROUP
```
---
### Usermod
Usermod its user to manage user which already exist

basic structure: usermod -OPTIONS LOGIN

- Options:
	- L: lock the user account 
	- U: unlock the user account
	- a: append the user to a supplementary group
	- G: specify a supplementary group

**Full command example**
```bash
usermod -a -G GROUPNAME USERNAME #To add an user to another group
usermod -L #To lock the login of an user
usermod -U #To unlock the login of an user
```

