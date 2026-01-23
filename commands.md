# Git Commands


### Initial Setup
* ``git init``: To initialise the repo
* ``git clone git@github.com:<your-account>/<repo-name>.git``: If cloning from an existing repository
* ``git remote add origin git@github.com:<your-account>/<repo-name>.git``: To add your local repository to GitHub

### Tracking changes

* ``git status``: To check current status
* ``git add .`` or ``git add <filename>``: Adding files to staging, all at once or specific files

### Saving changes

* ``git commit``: Opens a file to put descriptive commit messages
* ``git commit -m "commit message"``: If one-liner message is enough
* ``git log``: To check commit history

### Working with Branches

* ``git branch``: To list all branches
* ``git branch <feature-branch>``: To create a new branch
* ``git switch <feature-branch>``: To switch to the feature-branch
* ``git checkout -b <feature-branch>``: To create a new branch and switch to the same
* ``git branch -d <feature-branch>``: To delete the feature-branch

### Pull Requests (From a fork)

* ``git remote add <contributor> <fork-url>``: To locally add contributor's fork to your repo
* ``git fetch <contributor> <pr-branch-name>``: To get the pull request
* ``git checkout -b <branch-name> <contributor>/<pr-branch-name>``: Create and switch to pull request branch \
*-- Stage commits --*
* Merging:
    * ``git checkout main``
    * ``git pull origin main``
    * ``git merge <branch-name>``
    * ``git push origin main``\
*--Close PR--*

### Pull Requests (from a fork, but you need to work on it before merging)


*--Remotely add the fork, fetch and checkout--*

* ``git merge <contributor>/<pr-branch-name> --no-commit --no-ff``: Applies all PR changes without commiting anything yet. You can find deleted files.
* To restore those deleted files:
    * ``git restore --source=origin/main path/to/deletedFile`` or
    * ``git checkout origin/main -- path/to/deletedFile``

*--Make required changes, stage and make commits--*\
*--Checkout to main, merge the branch, push to main--*