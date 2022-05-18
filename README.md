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
### Show last committed file
`git show summary`

---
## Fix Specific Situations

### To update in my local master branch, and on my forked repo
- Ensure local branch is on master, because we want to merge into local master, from upstream master `git checkout master`
- fetch changes from upstream to local `git fetch upstream`
- merge changes from fetched upstream master branch to to local master branch `git merge upstream/master` this will merge into whatever the current selected branch is, from the name provided as a parameter
- push changes to forked repo (users repo) `git push origin master`

### Rebase my local feature (or develop) branch on top of latest changes to upstream master
- We want to do this to keep a clean Git history, or to be able to say "I'm working on my feature from the lastest version of master everyone else is using"
- follow steps above to update local master, then do the following:
- `git checkout develop`
- `git rebase master`
- WARNING: NEVER rebase on a public branch


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

## Searching Tools
### Find file in local drive/folder
`find . -name "filename.txt"`
