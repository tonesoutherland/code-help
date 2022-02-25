## General
### Clone repo to local from existing
`git clone https://github.com/<user-name>/<repo-name>.git`
### Show all branches
`git branch -va`
### Show status in current folder
`git status`
### Commit with message
`git commit -m "message"`
### Push changes to remote
`git push`
### Fetch upstream changes
`git fetch upstream`
### Change branch
`git checkout <branch-name>`
### Merge branch with upstream
`git merge upstream/<branch-name>`
### Show history using alias
`git logg` 

---
## Aliases
### Create alias for git log
`git config --global alias.logg "log --graph --decorate --pretty=oneline --abbrev-commit --all"`
### Show aliases
`git config --get-regexp alias`

