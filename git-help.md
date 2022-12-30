## General Commands 
### Clone repo to local from existing
- `git clone https://github.com/<user-name>/<repo-name>.git`
### Show all branches
- `git branch -va`
### Show status in current folder
- `git status`
### Commit with message
- `git commit -m "message"`
### Push changes to origin (on server)
- `git push`
### Show remotes
- `git remote -v`
### Fetch upstream changes - fetch does NOT merge w/local
- `git fetch upstream`
### Change branch
- `git checkout <branch-name>`
### Merge branch with upstream, then push to update fork
- `git merge upstream/<branch-name>`
- `git push`
### Show history using alias
- `git logg` 
### Show last committed file
- `git show summary`
### Abandon file changes
- `git restore .`
- `git restore <filename>`

---
## Purposeful Workflows

### To stash my changes, fetch and merge from a branch, and pop my stash
- Check status
    - `git status`
- Stash changes - this will stash tracked and untracked changed files
    - `git stash --include-untracked`
- Verify stash happened and that your working status is clean
    - `git status`
- Fetch and merge changes from desired branch
    - `git pull <remote-name> <remote-branch-name>`
- Assuming fast-forward occurs (no manual merging needed), then pop changes off stash
    - `git stash pop`

### To update in my local master branch, and on my forked repo
- Ensure local branch is on master, because we want to merge into local master, from upstream master 
    - `git checkout master`
- fetch changes from upstream to local 
    - `git fetch upstream`
- merge changes from fetched upstream master branch to to local master branch. this will merge into whatever the current selected branch is, from the name provided as a parameter
    - `git merge upstream/master`
- push changes to forked repo in Github (developer's repo) 
    - `git push origin master`

### Rebase my local feature (or develop) branch on top of latest changes to upstream master
- We want to do this to keep a clean Git history, or to be able to say "I'm working on my feature from the latest version of master everyone else is using"
- This needs to happen with the feature branch checked out
- follow steps above to update local master, then do the following:
    - `git checkout develop`
    - `git rebase master`
- WARNING: NEVER, EVER, EVER rebase on a public branch

#### Alternate flow - combines git fetch and git merge with rebase in one nice step
Do this while whatever feature branch your are working on is checked out
- `git pull upstream master --rebase`
- `git push origin feature-branch-name --force` (--force is required, otherwise it won't be allowed)
	
- If there are merge conflicts
    - `git mergetool` .. or use your merge tool of choice (Visual Studio, VS Code)
	- `git commit -am "Fix merge conflicts"` commit the final versions of the merged file(s)
    - `git rebase --continue` tell the rebase to continue
	- `git push origin feature-branch-name` push to your origin, `--force` should not be required here

### Test code from a co-worker's remote branch
- when a co-worker submits a PR and you want to pull to your local and verify before approving
    - `git remote add <remote-name> https://github.com/<username>/<repo-name>.git`
    - `git fetch <remote-name> <branch-name-source>:<branch-name-target>`
    - `git checkout <branch-name>`
- note 1: add the remote to the users repo, NOT the repo with branch
- note 2: the branch name must be different (unsure why)

### Test code from a PR
- when a co-worker submits a PR and you want to pull and test, but from the PR branch in Github, instead of the co-workers direct repo
- Fetch the reference to the pull request based on its ID number, creating a new branch in the process.
    - `git fetch <remote-name> pull/<PR-ID#>/head:<branch-name>`
        - ex: `git fetch upstream pull/59/head:feature-KINT-198`
    - [Github - Checking out Pull Requests locally](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/checking-out-pull-requests-locally)

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
### Create aliases to publish new branch
- `git config --global alias.branch-name "rev-parse --abbrev-ref HEAD"`  
- `git config --global alias.pub "git push -u origin $(git branch-name)"`  
This allows you to run `git pub` to push your new local branch to the repo
### Show aliases
- `git config --get-regexp alias`

---
## Useful links
- [Branching basics - remote branching](https://git-scm.com/book/id/v2/Git-Branching-Remote-Branches)
- [Clean up a fork and restart from upstream](https://stackoverflow.com/questions/9646167/clean-up-a-fork-and-restart-it-from-the-upstream)

## Searching Tools
### Find file in local drive/folder
- `find . -name "filename.txt"`
