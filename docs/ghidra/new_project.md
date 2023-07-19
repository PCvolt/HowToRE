## New Project
When launching Ghidra, you are faced with a project launcher.

1. Create a project directory to hold the project you will work in
2. Put a copy of the file you want to examine in this folder
3. ``File > New Project...`` in non-shared, indicate the folder you just created and continue
4. Drag&Drop the file onto the launcher where the named folder is
5. Double-click the file to open it
6. The default parameters should be fine, let Ghidra disassemble/decompile your file for a few minutes*
7. You can now start digging

*Ghidra may complain that there is no PDB. Ignore it. The PDB is the debugging file only present in the Debug mode of the executable/dll/file, or more realistically only to the original developers.
<br>It contains the names of all functions, variables and anything else, and it's precisely because you are missing this file that you will spend hours finding out what this FUN_006452C2 does.