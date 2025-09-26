# Git

[Git](https://git-scm.com/) is a popular version control system.

* concepts
    * working directory vs repository
    * [branchs](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell): master (default), feature branchs, develop, bugfixes branchs, etc.
    * HEAD is a reference to the last commit in the currently checked-out branch
    * a detached HEAD is the situation you end up in whenever you check out a commit (or tag) instead of a branch. In this case, you have to imagine this as a temporary branch without a name.
    * [.gitignore](https://git-scm.com/docs/gitignore)
      to specifies intentionally untracked files to ignore
    * staging area: is a place to record things that will be committed
    * branch types
        * _local_ branch:
          branch on your machine only
        * _remote_ branch:
          branch in remote repository (e.g. GitHub)
        * _remote-tracking_ branch:
          local (read-only) copy of connected remote branch
          ; use `git fetch` to update with remote states
        * _local-tracking_ branch:
          editable branch on your machine connected to remote branch
          ; use `git pull` / `push` to get/update remote branch
    * [githooks](https://git-scm.com/docs/githooks)
      are programs you can place in a hooks directory to trigger actions at certain points in git’s execution; see [Git Hooks guide](https://githooks.com/)
* commands
    * [git init](https://git-scm.com/docs/git-init)
      to create an empty Git repository
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
          (it's a shortcut to `git branch feature/xyz` + `git checkout feature/xyz`)
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
            * rebase is not recommended for shared repositories because it rewrites the history
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
            * `git remote` to show servers
        * [git clone](https://git-scm.com/docs/git-clone)
          to clone a repository into a new directory
        * [git branch -a](https://git-scm.com/docs/git-branch)
          to list all local, local/remote-tracking branches
        * [git branch --track](https://git-scm.com/docs/git-branch)
          `feature-remote origin/feature-remote`
          to create a local-tracking branch
        * [git push](https://git-scm.com/docs/git-push)
          to update remote with local changes
            * [git push](https://git-scm.com/docs/git-push) `-u origin feature-local` to push local branch to remote repository 
              (non-existing yet remote) and make it as local-tracking branch
        * [git pull](https://git-scm.com/docs/git-pull)
          to incorporates changes from a remote repository into the current branch
        * [git fetch](https://git-scm.com/docs/git-fetch)
          to update remote tracking branches (local) by downloading
          states on remote repository (e.g. new branches);
            * `git fetch` does not update local branches, use `git pull` to do it
            * [git branch --delete --remotes](https://git-scm.com/docs/git-branch) `origin/feature` to delete remote-tracking branch
            * [git push](https://git-scm.com/docs/git-push) `origin --delete feature`
              to delete remote branch (and remote-tracking branch as well)
* best-practises
    * [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) workflow
      mainly used with entreprise enviroment, having bugfix branches, releases, etc.
    * [Trunk-based development](https://www.atlassian.com/continuous-delivery/continuous-integration/trunk-based-development)
      where developers merge small, frequent updates to a core “trunk” or main branch
        * use continuous integration/[continuous deployment](https://www.atlassian.com/continuous-delivery)
        * [feature toggle/flag](https://www.atlassian.com/continuous-delivery/principles/feature-flags) are used to prevent to activate new feature too early
    * [Forking workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow) used in open source project in GitHub
        * contributor does not clone the remote repository but fork/make a copy of the remote repository in his own GitHub account
        * contributor create pull-requests of new feature/bugfix that is reviewed by team members of the origin remote repository
    * [Guidelines about commit message](https://github.com/angular/angular/blob/main/contributing-docs/commit-message-guidelines.md) 
* [references](https://git-scm.com/docs)
    * [tutorial](https://git-scm.com/docs/gittutorial)
    * online [Pro Git book](https://git-scm.com/book/en/v2)
    * [getting started](https://www.atlassian.com/git/tutorials/setting-up-a-repository)

[*Go to parent page*](README.md)

*(Page mainly written in April 2023; links checked on 19.02.2024)*
