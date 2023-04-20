# Git

[Git](https://git-scm.com/) is a popular version control system.

* concepts
  * working directory vs repository
  * [branchs](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell): master (default), feature branchs, develop, bugfixes branchs, etc.
  * HEAD is a reference to the last commit in the currently checked-out branch
  * a detached HEAD is the situation you end up in whenever you check out a commit (or tag) instead of a branch. In this case, you have to imagine this as a temporary branch without a name.    
  * [.gitignore](https://git-scm.com/docs/gitignore)
    to specifies intentionally untracked files to ignore
  * staging area: is a place to record things that will be commit
* commands
  * [git init](https://git-scm.com/docs/git-init) 
    to create an empty Git repository
  * [git clone](https://git-scm.com/docs/git-clone) 
    to clone a repository into a new directory
  * [git config](https://git-scm.com/docs/git-config) 
    to get and set repository or global options
    * e.g. `git config --global user.email "yourEmail@xyz.com"`
  * [git status](https://git-scm.com/docs/git-status) 
    to show the working tree status
  * [git add](https://git-scm.com/docs/git-add)
    to add file contents to the index
    * `git add .` to add all files to staging area
  * [git commit](https://git-scm.com/docs/git-commit) -m _message_
    to record changes to the repository
  * [git log](https://git-scm.com/docs/git-log)
    to show commit logs
  * [git checkout](https://git-scm.com/docs/git-checkout)
    to switch branches or restore working tree files
    * `git checkout -b feature/xyz` create a branch and switch to it 
      (its a shortcut to `git branch feature/xyz` + `git checkout feature/xyz`)
    * `git checkout commitid` to checkout a commit as detached HEAD
  * [git switch](https://git-scm.com/docs/git-switch)
    to create/switch branches (similar to git checkout but for branches only)    
  * [git branch](https://git-scm.com/docs/git-branch)
    to list, create, or delete branches
  * [git merge](https://git-scm.com/docs/git-merge)
    to join two or more development histories together
  * [git ls-files](https://git-scm.com/docs/git-ls-files)
    to show information about files in the index and the working tree
  * delete commands
    * [git rm](https://git-scm.com/docs/git-rm)
      to remove files from the index after having deleted from working directory
    * [git restore](https://git-scm.com/docs/git-restore)
      to revert changes in tracked files
      * `git restore .` to revert changes in all tracked files
    * [git clean -df](https://git-scm.com/docs/git-clean)
      to remove untracked files from the working tree
      * `git clean -dn` to have a preview of recursive remove
    * [git restore --staged filename](https://git-scm.com/docs/git-restore)
      to remove file(s) from staging area
      * `git restore --staged .` to remove all file from staging area
    * [git reset [--soft|--hard] HEAD~1](https://git-scm.com/docs/git-reset)
      to undo latest commit
    * [git branch -D branchname](https://git-scm.com/docs/git-branch)
      to remove branch
  * [git stash [push]](https://git-scm.com/docs/git-stash)
    to saves your local modifications away
    * `git stash list` list the modifications stashed away
    * `git stash show` inspect the stashed modifications
    * `git stash apply` restore modification
* best-practises
  * [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) workflow
* [references](https://git-scm.com/docs)
  * [tutorial](https://git-scm.com/docs/gittutorial)
  * online [Pro Git book](https://git-scm.com/book/en/v2)
* TODO
  * [git stash](https://www.atlassian.com/git/tutorials/saving-changes/git-stash)
  * git merge vs [git rebase](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase) ?
  * [git hooks](https://githooks.com/) useful?

*(Page mainly written in April 2023)*

[*Go to parent page*](../README.md)
