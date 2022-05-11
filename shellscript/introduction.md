# Shellscript Basics

### Var declaration and attribuitio
name=value

### Var read
echo $name #Must output "value"

### env,unset,export
- env: the env command will show you every environtment variable
- unset <varname>: will delete a variable value
- export <varname>: will make a variable global(which means he can be accessed everywhere

### Arrays
- declaration: array=(value1 value2 value3)
- select element: ${array[index]}
- select all elements: ${array[*]}
- declaration of specific element: array[index]=value
- delete one element: unset array[index]
- delete all elements: unset array[*]

