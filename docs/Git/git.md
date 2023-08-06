## Git
Git is used both locally (your project directory) and remotely (github/gitlab) for version controlling.

This means creating saves and a history of what has been done during the whole project. However, those saves can be edited to your liking to make "cleaner" saves and the history can be edited as well to reflect a clean timeline.

### Cleaning your code before even using Git
1. Install pre-commit on your computer: ``pip install pre-commit``
2. Install pre-commit in your repository: ``pre-commit install``
3. Before any git add, run ``pre-commit run --all`` so your code is all nicely formatted

Congrats, you don't even have to bother with indenting yourself.

---
### Hash
Commits all have a **hash**, an identifier so to speak.
<br>**HEAD** is the pointer to the latest commit you performed(?)

```ruby
commit d66b78231f26cb7cf738678bea1d081b8b4def71 (HEAD -> main, origin/main)
Author: PC_volt <this is private>
Date:   Sun Aug 6 18:40:14 2023 +0200
```

You can point anywhere, but if you are not pointing to the HEAD, you will be in a **detached HEAD** state.

---
### Git the easy and dirty way
It is dirty in the sense that you have no care for the history and only the result counts.
This is acceptable for smaller projects, or don't want to bother if you are in a small team.

``git add -A``
<br>``git commit -m "<msg>"``
<br>``git push``