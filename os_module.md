# Dirs
- Change Directory: os.chdir("absolute-path")
- List Dirs: os.listdir("absolute-path")
- Make Dir: os.mkdir("dirname")
- Rename a Dir: os.rename("dirname","new-dir-name")
- Check if a dir exist or not and return a bool: os.path.isdir("dirname")
- Remove a tree of directories: shutil.rmtree("dirname")

# Files
- Create a file: open("file-name",mode="")
- Remove a File: os.remove("file-name")
- Rename a File: os.rename("file-name","new-file-name")
- Check if a file exist or not and return a bool: os.path.isfile("absolute-path/file-name")

# Paths 
- 

# Modules
To create a module its necessary to follow this steps
1. create a dir called "modules"
2. add the path from your project(where the code of you API is) at this way: "export PYTHONPATH="${PYTHONPATH}:/the/path/of/your/project"
