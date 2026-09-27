# Navigation

In linux, files are stored in like a tree like structure which is referred as a hiearchecal directory structure
The first directory in linux is referred as the root directory which have further files and subdirectories and the files and subdirectories have further files and subdirectorires. Linux file systems will have a single filesystem tree 

The directory a user is currently inside is the current working directory, to know at which location the user is they tend to use pwd. 

For changing directories we tend to use cd. A pathname is a route we take along the branches of the tree to reach the final location. There are two types of pathnames 
Absolute 
Relative 

Absolute pathname begin from the absolute beginning (Root directory) and follow branch by branch to the target directory 

Example:
cd /usr/bin 
Pwd
/usr/bin

Relative Pathnames:
Pathnames that tend to start from the working directory all the way to the target directory. 

Notations for parent directory
(.) Suggests The working directory 
(..) Suggests the parent directory

Major Shortcut 
Use cd - to change directory back to the previous directory. 

Major factors About Filenames:
FN beginning with periods tend to be hidden file 
FN and commands are case sensitive 

## Terminal Command Sequence

```bash
# 1. Absolute Pathname
-(kali@kali)-[/usr/bin]
-$ cd /usr/bin

# 2. Moving to absolute path /usr
-(kali@kali)-[/usr/bin]
-$ cd /usr

# 3. Relative Pathname using current directory notation (.)
-(kali@kali)-[/usr]
-$ cd ./bin

# 4. Re-navigating via absolute path
-(kali@kali)-[/usr/bin]
-$ cd /usr/bin

# 5. Displaying Current Working Directory with pwd
-(kali@kali)-[/usr/bin]
-$ pwd
/usr/bin
