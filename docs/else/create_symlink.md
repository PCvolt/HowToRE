## Creating a Symbolic Link (Symlink)
A Symbolic Link is a file that points to another file or directory.

It is used for "connecting" a folder to another, like in the case of assets, you will not be required to move your assets output directory to the project itself.

Command line: ```mklink /D  "C:\Pictures\assets" "C:\git\project\assets"```

*The folder in the second string must not exist before!*

Deleting a SymLink has no effect on any file. It also must be manually updated.  
