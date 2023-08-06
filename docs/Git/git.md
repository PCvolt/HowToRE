## Git
The goal is to have a clean history, by selectively staging and committing pieces of the code.
For example, instead of writing a function over multiple commits, you want to have this function being added in the history in its own commit.

### Cleaning your code before even using Git
1. Install pre-commit on your computer: ``pip install pre-commit``
2. Install pre-commit in your repository: ``pre-commit install``
3. Before any git add, run ``pre-commit run --all`` so your code is all nicely formatted

Congrats, you don't even have to bother with intending yourself.

## Git the easy and dirty way
It is dirty in the sense that you have no care for the history and only the result counts.
This is acceptable for smaller projects, or don't want to bother if you are in a small team.

``git add -A``
``git commit -m "<msg>"``
``git push``

``git branch <branch-name>`` creates the branch
``git checkout -b <branch-name>`` creates the branch and switch to it
``git checkout <branch-name>`` switches to the branch