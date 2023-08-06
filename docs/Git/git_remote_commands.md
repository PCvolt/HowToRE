## Git Remote Commands
These commands are aimed to be used when you have a remote repository like Github or Gitlab set up.

### Git Fetch
``git fetch``
<br>Fetches the changes from the remote but doesn't incorporate them into the local. Use ``git merge`` or ``git rebase`` to get your local repository updated.

---
### Git Pull

``git pull``
<br>It is essentially a ``git fetch`` followed by a ``git merge``.
<br>Pulls the commits of the remote repository into the local repository. Always do this before pushing to avoid conflicts.

---
### Git Push

``git push``
<br>Pushes the committed changes towards the remote repository.
<br>When the history of the commits doesn't match the one in the remote, this is when you will may have to use responsibly the ``--force`` flag. 