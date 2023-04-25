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
  * remote-tracking branch; is a local read-only branch that is connected to a remote branch
    * when you push and pull on that branch, it automatically pushes and pulls to the remote branch that it is connected with
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
  * merge commands  
    * [git merge](https://git-scm.com/docs/git-merge)
      to join two or more development histories together
      * `git merge --abort` to abort a merge (in case of conflict)
      * most common [merge strategies](https://git-scm.com/docs/merge-strategies):
        * [fast-forward](https://git-scm.com/docs/git-merge#_fast_forward_merge) happens by merging on a branch having no changes; only the HEAD is updated (without any additional commit)
        * recursive merge (non fast-forward): happens by merging on a branch having already commits. An additional commit is required
      * see [merge conflicts](https://git-scm.com/book/en/v2/Git-Tools-Advanced-Merging#_advanced_merging)  
    * [git-rebase](https://git-scm.com/docs/git-rebase)
      change the base (parent commit) & reapply commits
      * rebase is not recommended for shared repositories because it rewrite the history
      * see [git merge vs rebase](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
    * [git cherry-pick](https://git-scm.com/docs/git-cherry-pick)
      to apply the changes introduced by some existing commits
  * [git diff](https://git-scm.com/docs/git-diff)
    to show changes between commits, commit and working tree, etc
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
    * `git stash pop` removes the changes from your stash and reapplies them to your working copy
    * `git stash apply` reapply the changes to your working copy and keep them in your stash
    * `git stash list` list the modifications stashed away
    * `git stash show` inspect the stashed modifications
  * [git reflog](https://git-scm.com/docs/git-reflog) display reference logs; usefull id of lost commits
  * [git tag](https://git-scm.com/docs/git-tag)
    create, list, delete or verify a tag; e.g. a release
  * remote commands
    * [git remote](https://git-scm.com/docs/git-remote)
      to manage set of "remote" repositories
      * `git remote add name url` to add an alias of the URL of the remote repository (origin is often used as default name)
    * [git push](https://git-scm.com/docs/git-push)
      to update remote with local changes
    * [git pull](https://git-scm.com/docs/git-pull)
      to incorporates changes from a remote repository into the current branch
    * [git branch -a](https://git-scm.com/docs/git-branch)
      to list both remote-tracking branches and local branches.
* best-practises
  * [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) workflow
* [references](https://git-scm.com/docs)
  * [tutorial](https://git-scm.com/docs/gittutorial)
  * online [Pro Git book](https://git-scm.com/book/en/v2)
  * [getting started](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
* TODO
  * [git hooks](https://githooks.com/) useful?

*(Page mainly written in April 2023)*

[*Go to parent page*](../README.md)