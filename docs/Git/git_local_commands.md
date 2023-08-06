## Git Local Commands
Rundown of the most common git commands.

### Git Add
Git add allows to include the selected files or lines of code to be 

``git add --all`` or ``git add -A``
<br>The git add command by default!
<br>It stages the entire repository, be it new files, modifications and deletions.

``git add -p`` (``-p`` stands for patch)
<br>Allows you to interactively review and apply patches on the code you want to stage.
<br>This inherently makes your files in your repository potentially different from the files you are staging for the commit.

Hunks are groups of differing lines, and you decide which actions to apply:
- ``y``: stage this hunk
- ``n``: do not stage this hunk
- ``s``: split into smaller hunks
- ``e``: edit this hunk
- ``q``: quit and do not stage any more hunks
- ``?``: help
As you can see, this is the most complex but most useful for keeping a clean history, free of commented-out portion of codes.

<details><summary>Other commands</summary>

``git add <file1 file2>``
<br>Stages the indicated files. Maybe the command you've seen first, but not really useful since you will be most of the time staging a lot of files. Plus, writing all the filenames is pretty long.

``git add .`` (``.`` stands for the current directory)
<br>This command works like ``git add --all`` but:
- it does **not** stage file deletions
- it does **not** stage anything above the current directory

``git add -u`` (``-u`` stands for update)
<br>This command works like ``git add --all`` but:
- it does **not** stage new files
- it does **not** stage anything above the current directory

``git add -i`` (``-i`` stands for interactive)
<br>This command provides an interface to perform diverse tasks like status, update, revert, add, patch or diff. Maybe the most interesting but complex command here.
</details>

---
### Git Commit

``git commit -m <msg>``
<br>The standard git commit. Use this.

``git commit --amend``
<br>When you did a little mistake on the content or the commit message, and don't want to make a fully dedicated commit to fixing it.
You then just edit the latest commit with this.

<details><summary>Other commands</summary>

``git commit -p``
<br>Works just like git add -p, but for commits.
Using the staged files (with any git add command), you can decide the patches to apply to the files that will be committed.
</details>