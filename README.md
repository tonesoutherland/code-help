### General
#### Clone repo to local from existing
`git clone https://github.com/<user-name>/<repo-name>.git`
#### Show all branches
`git branch -va`
#### Show status in current folder
`git status`
#### Commit with message
`git commit -m "message"`
#### Push changes to remote
`git push`
#### Show remotes
`git remote -v`
#### Fetch upstream changes
`git fetch upstream`
#### Change branch
`git checkout <branch-name>`
#### Merge branch with upstream, then push to update fork
`git merge upstream/<branch-name>`
`git push`
#### Show history using alias
`git logg` 

---
### Aliases
#### Create alias for git log
`git config --global alias.logg "log --graph --decorate --pretty=oneline --abbrev-commit --all"`
#### Show aliases
`git config --get-regexp alias`

