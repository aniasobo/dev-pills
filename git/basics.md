# Git basics

### ▶️ Start with `git init`

### ❌ Remove with `rm -rf .git`

### ↩️ Remove and unstage with `git rm fileToRemoveAndUnstage.txt`

### 🔙 Checkout a specific commit with `git checkout <last 4 digits of commit hash>`

### 📝 List active remotes with `git remote -v`

### 🔂 Create a branch and switch to it with `git checkout -b branch-name`

### Add current main to your branch:

1. `git checkout main`
2. `git pull`
3. `git checkout branch-name`
4. `git merge main`
   (go the other way to merge your branch to your local main)

### 📌 Pull everything to local repo for offline work with `git fetch origin`

### 🔭 View your remote branches with `git branch --remote`

### Pushing local branch to remote: `git push origin branch-name`

### 🔫 Delete branch: `git branch -d branch-name`

### 😳 Rename current branch: `git branch -m newName`

### 😬 Rename another branch: `git branch -m oldName newName`

## On a feature branch branched out of a higher level feature branch:

`git pull` = `git fetch` + `git merge` against tracking upstream branch

`git pull --rebase` = `git fetch` + `git rebase` against tracking upstream branch

To stop a rebase do a `git rebase -a` abort ??

Procedure:

1. switch from own branch to feature branch
2. pull latest changes to feature branch
3. switch back to own branch
4. `git rebase feature/branch`
5. solve each conflict, then force push

### To check what's been changed before writing a commit message: `git diff`

---

## Notes from a git workshop

**git rebase tip:**

run `git rebase main` from your branch to move it forward in time. commit first.

`git checkout main^` - checks out the parent of main.

`git checkout main^^` - checks out the grandparent of main.

`git checkout HEAD^` - move back/up a level in the commit tree (ie go back in time with commits).

`git checkout HEAD~4` - move back four times.

reassign a branch to a commit in the past: `git branch -f main HEAD~4` - forces main to the commit that is 4 parents behind HEAD.

`git reset HEAD~1` - moves branch back a commit as if the changes never happened; good solution for **local branches**

`git revert HEAD` - introduces a change to your remote but that change is undoing - so that others can update their copies of your branch to this new state; good fore **remotes**

`git cherry-pick <commit> <commit><c...` - puts specified commits below current HEAD

interactive rebase: `git rebase -i HEAD~4` - vim window with the last 4 commits behind HEAD opens up and allows you to drag/drop commits to rearrange commit history

moving only one commit to main (ex. result of bug fix without the whole debugging history):
`git rebase -i` followed by `git cherry-pick`, example:
`git checkout main` - moves from branch to main
`git cherry-pick <commit>` - adds the chosen commit only to main

mark commits that are milestones with git tags: `git tag <tag> <commit hash>`

`git describe <ref>` - ref can only be something that can be resolved into a commit; default is HEAD; outputs:
`<tag>_` - closest ancestor tag in history
`<num commits>_` - how many commits away that tag is
`_g<hash>` - the hash of the commit being described

**rebasing multiple branches**

`git checkout HEAD^2` - checks out the second parent
`git checkout HEAD~^2~2` - moves up one level, then to the second parent, then up 2 levels over that parent;

**remotes**

`git fetch` - gets data from a remote, and updates the local representation of that remote; it downloads the commits that the remote has but the local repo does not (say, added by other people); it then updates where the remote branches point
