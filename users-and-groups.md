# Users and Groups
On Linux we have 5 most common commands to create, delete and manage users, which is(useradd, userdel, groupadd, groupdel and usermod)

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
basic structure:

