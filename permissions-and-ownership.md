# Permissions and Ownership on Linux 

On linux we have 3 types of permission, Read, Write and Execute which we can specify for Files and Dirs through the command **Chmod**

### Chmod Octal

Assume: Read = 4, Write = 2, Execute = 1, now, if you want to make a file Readable and Executable you need to sum 4 + 1, which is 5, keep that idea

on chmod, we first define permission for the Owner, them for the others(user from the same group of the owner) and all(any user on the system),**Full Example:**

```bash
chmod 777 file #Setting permisions of Reading, Writing and Execution for the Owner, any user of his group and anyone on the system.
```

We set Read, Write and Execute permission for the owner, others and all.

### Chmod Ugoa

**Target of Permission**
- u: User(owner of the file)
- g: Group(Users of the same group)
- o: Others(User which not belong of the same group of the owner)
- a: All(Anyone on the system)

**Type of Permission**
- R: Read
- W: Write
- X: Execute

**Adding, Removing and Redefining**
- +: Will add new permissions
- -: Will remove permission
- =: Will reset and and then set new permissions

**Full Example:**

```bash
chmod ug+wx file #Here im saying "add new permissions of writing and execution for the Owner and any user on his group"
```

### Chown and Chgrp

Chown command is used to change the owner and group of a file or dir, we need to specify the name of the user, the group and then the file, like this:
```bash
chown user:group file
```

Chgrp is quite similar, the only difference him and Chown, its about the fact he can just change the group of the file, look:
```bash
chgrp group file
```

### Options
- -c: Allow you to change more than one file/dir specifying then after the option
- -R: Will change the permissions recursively(Which means every subdir will also have your permissions changed) 
