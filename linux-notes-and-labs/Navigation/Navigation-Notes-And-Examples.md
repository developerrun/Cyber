# Navigation

* In Linux, files are stored in a tree-like structure which is referred to as a hierarchical directory structure.
* The first directory in Linux is referred to as the root directory, which has further files and subdirectories, and the files and subdirectories have further files and subdirectories.
* Linux file systems have a single filesystem tree.
* The directory a user is currently inside is the current working directory. To know at which location the user is, they tend to use `pwd`.
* For changing directories, we tend to use `cd`. 
* A pathname is a route we take along the branches of the tree to reach the final location. There are two types of pathnames:
  * **Absolute Pathnames**
  * **Relative Pathnames**

## Pathname Types

* **Absolute Pathnames:** Begin from the absolute beginning (root directory) and follow branch by branch to the target directory.
  * Example:
    ```bash
    cd /usr/bin
    pwd
    /usr/bin
    ```
* **Relative Pathnames:** Pathnames that tend to start from the working directory all the way to the target directory.

## Directory Notations
* `.` suggests the working directory.
* `..` suggests the parent directory.

## Major Shortcut
* Use `cd -` to change directory back to the previous directory.

## Major Factors About Filenames
* Filenames beginning with periods tend to be hidden files.
* Filenames and commands are case-sensitive.

## Terminal Command Sequence
```bash
# Absolute pathname
-(kali@kali)-[/usr/bin]
-$ cd /usr/bin

# Absolute path to /usr
-(kali@kali)-[/usr/bin]
-$ cd /usr

# Relative pathname using current directory notation (.)
-(kali@kali)-[/usr]
-$ cd ./bin

# Absolute pathname re-navigation
-(kali@kali)-[/usr/bin]
-$ cd /usr/bin

# Printing working directory with pwd
-(kali@kali)-[/usr/bin]
-$ pwd
/usr/bin
