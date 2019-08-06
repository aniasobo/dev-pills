# Git basics

### ▶️ Start with `git init`  

### ❌ Remove with `rm -rf .git`  

### ↩️ Remove and unstage with `git rm fileToRemoveAndUnstage.txt`  

### 🔙 Checkout a specific commit with `git checkout <last 4 digits of commit hash>`  

### 📝 List active remotes with `git remote -v`  

### 🔂 Create a branch and switch to it with `git checkout -b branch-name`  

### Add current master to your branch:
1. `git checkout master`  
2. `git pull`  
3. `git checkout branch-name`  
4. `git merge master`  
(go the other way to merge your branch to your local master)  

### 📌 Pull everything to local repo for offline work with `git fetch origin`  

### 🔭 View your remote branches with `git branch --remote`  

### Pushing local branch to remote: `git push origin branch-name`  

### 🔫 Delete branch: ` git branch -d branch-name`  


