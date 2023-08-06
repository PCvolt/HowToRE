## The history

The reason we do that is because simply using ``git merge`` into the master will cause a lot of conflicts when working with other devs.
<br>Since merging implies creating a new commit in the main, it will also create conflicts to resolve 

Commits all have a **hash**, an identifier so to speak.
<br>**HEAD** is the pointer to the latest commit you performed. 

```ruby
commit d66b78231f26cb7cf738678bea1d081b8b4def71 (HEAD -> main, origin/main)
Author: PC_volt <this is private>
Date:   Sun Aug 6 18:40:14 2023 +0200
```

You can point anywhere, but if you are not pointing to the HEAD, you will be in a **detached HEAD** state.


More here : [Atlassian: Rewriting History](https://www.atlassian.com/git/tutorials/rewriting-history)

---
### Git Commit --amend
Note that the modified commits are actually new commits.
<br>Be very careful not to --amend a commit on which someone else is developing. 

``git commit --amend -m "message"`` modifies the commit and replaces the message. 
<br>``git commit --amend --no-edit`` modifies the commit without changing the original message.

---
### Git Reset
Git reset moves the HEAD

``git reset HEAD``


---
### Git Rebase
``git rebase`` directly interacts with the ramification of the tree.

Instead of merging and creating a new commit for implementing the changes, the commits of the branch are duplicated on top of the HEAD.

Instead of having a ramified history, you create a linear history that is easier to understand.

The hash are different as well


``git rebase --interactive --autosquash``


---
### Git Revert

``git revert <commit-hash>``