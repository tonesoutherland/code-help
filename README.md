## General Commands
### Clone repo to local from existing
`git clone https://github.com/<user-name>/<repo-name>.git`
### Show all branches
`git branch -va`
### Show status in current folder
`git status`
### Commit with message
`git commit -m "message"`
### Push changes to origin (on server)
`git push`
### Show remotes
`git remote -v`
### Fetch upstream changes - fetch does NOT merge w/local
`git fetch upstream`
### Change branch
`git checkout <branch-name>`
### Merge branch with upstream, then push to update fork
`git merge upstream/<branch-name>`
`git push`
### Show history using alias
`git logg` 

---
## Fix Specific Situations

### Test code from a co-worker's remote branch
`git remote add <remote-name> https://github.com/<username>/<project-name>.git`
`git fetch <remote-name> <branch-name-source>:<branch-name-target>`
`git checkout <branch-name>`

### If forked repository is out of sync with upstream
- delete master branch: `git branch -D master`
- fetch changes from upstream: `git fetch upstream`
- make sure you are on master branch: `git checkout master`
- perform a hard reset to upstream/master: `git reset --hard upstream/master`
- force push to your forked repository: `git push origin master --force` 

### Update local repo when working in dev branch with local only temp changes
_user is on develop branch_
- pull in changes from upstream: `git fetch upstream`
- stash unstaged changes on develop branch: `git stash`
- checkout master branch: `git checkout master`
- merge master: `git merge upstream/master`
- checkout develop branch: `git checkout develop`
- unstash changes: `git stash pop`

---
## Aliases
### Create alias for git log
`git config --global alias.logg "log --graph --decorate --pretty=oneline --abbrev-commit --all"`
### Show aliases
`git config --get-regexp alias`

---
## Useful links
- [Branching basics - remote branching](https://git-scm.com/book/id/v2/Git-Branching-Remote-Branches)
- [Clean up a fork and restart from upstream](https://stackoverflow.com/questions/9646167/clean-up-a-fork-and-restart-it-from-the-upstream)
