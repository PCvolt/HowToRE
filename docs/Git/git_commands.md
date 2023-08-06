### Git Add
Git add allows to include the selected files or lines of code to be 

``git add --all`` or ``git add -A``
The git add command by default!
It stages the entire repository, be it new files, modifications and deletions.

``git add -p`` (``-p`` stands for patch)
Allows you to interactively review and apply patches on the code you want to stage.
This inherently makes your files in your repository potentially different from the files you are staging for the commit.
Hunks are groups of differing lines, and you decide which actions to apply:
- ``y``: stage this hunk
- ``n``: do not stage this hunk
- ``s``: split into smaller hunks
- ``e``: edit this hunk
- ``q``: quit and do not stage any more hunks
- ``?``: help
As you can see, this is the most complex but most useful for keeping a clean history, free of commented-out portion of codes.

<details><summary>Other git add commands</summary>

``git add <file1 file2>``
Stages the indicated files. Maybe the command you've seen first, but not really useful since you will be most of the time staging a lot of files. Plus, writing all the filenames is pretty long.

``git add .`` (``.`` stands for the current directory)
This command works like ``git add --all`` but:
- it does **not** stage file deletions
- it does **not** stage anything above the current directory

``git add -u`` (``-u`` stands for update)
This command works like ``git add --all`` but:
- it does **not** stage new files
- it does **not** stage anything above the current directory

``git add -i`` (``-i`` stands for interactive)
This command provides an interface to perform diverse tasks like status, update, revert, add, patch or diff. Maybe the most interesting but complex command here.
</details>

### Git Commit

``git commit -m <msg>``
The standard git commit. Use this.

``git commit --amend``
When you did a little mistake on the content or the commit message, and don't want to make a fully dedicated commit to fixing it.
You then just edit the latest commit with this.

<details><summary>Other git add commands</summary>
``git commit -p``
Works just like git add -p, but for commits.
Using the staged files (with any git add command), you can decide the patches to apply to the files that will be committed.
</details>

### Git Reset

### Git Rebase

``git rebase --interactive --autosquash``