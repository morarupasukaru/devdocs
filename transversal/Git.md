# Git

[Git](https://git-scm.com/) is a popuplar version control system.

* concepts
  * working directory vs repository
  * [branchs](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell): master (default), feature branchs, develop, bugfixes branchs, etc.
  * HEAD is a reference to the last commit in the currently checked-out branch
  * a detached HEAD is the situation you end up in whenever you check out a commit (or tag) instead of a branch. In this case, you have to imagine this as a temporary branch without a name.    
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
  * [git commit](https://git-scm.com/docs/git-commit) -m _message_
    to record changes to the repository
  * [git log](https://git-scm.com/docs/git-log)
    to show commit logs
  * [git checkout](https://git-scm.com/docs/git-checkout)
    to switch branches or restore working tree files
    * `git checkout -b feature/xyz` create a branch and switch to it 
      (its a shortcut to `git branch feature/xyz` + `git checkout feature/xyz`)
  * [git switch](https://git-scm.com/docs/git-switch)
    to switch branches (similar to git checkout but for branches only)    
  * [git branch](https://git-scm.com/docs/git-branch)
    to list, create, or delete branches
  * [git merge](https://git-scm.com/docs/git-merge)
    to join two or more development histories together
* best-practises
  * [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) 

* references
  * online [Pro Git book](https://git-scm.com/book/en/v2)



*(Page mainly written in April 2023)*

[*Go to parent page*](../README.md)
