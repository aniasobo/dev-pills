# .gitignore

[Octocat's .gitignore rules](https://gist.github.com/octocat/9257657)

## My standard additions

```
# OSX
.DS_Store # excludes at root
/**/.DS_Store # excludes in all directories
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# Ignore all config
config/*

directory_to_ignore/

# Node
node_modules/

# SimpleCov
/coverage
coverage/**/*
```

## Make it global!

1. pick your choices
2. add them to global configuration `~/.gitignore_global`  
3. add it to your fresh git config with `git config --global core.excludesfile ~/.gitignore_global`

## Remove DS_Store post-push:

**[Removing DS_Store from a GitHub repo via .gitignore](https://stackoverflow.com/questions/107701/how-can-i-remove-ds-store-files-from-a-git-repository)**

magic line:

```
find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
```

run the above in terminal, then add `.DS_Store` to `.gitignore` & commit

[alternative way to do this](http://www.codeblocq.com/2016/01/Untrack-files-already-added-to-git-repository-based-on-gitignore/)
