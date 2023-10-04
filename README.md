# Git - Github

[Git docs](https://git-scm.com/docs)

- [ ] - optional

## Basic Git Commands

```
git init
```

```
git status
```

```
git add .
git add <filename1> <filename2>
```

```
git commit
git commit -m <message>
git commit -a -m <message>
git commit --amend
```

## Inspection and Comparison

```
git log
git log --oneline
```

- view only unstaged changes since last commit

```
git diff [<filename>]
```

- view only staged changes since last commit

```
git diff --staged [<filename>]
git diff --cached [<filename>]
```

- view ALL changes since last commit (staged + unstaged)

```
git diff HEAD [<filename>]
```

## Branching and Merging

- view branches

```
git branch
```

- view branches with details

```
git branch -v
git branch --verbose
```

- create a branch

```
git branch <branch-name>
```

- rename a branch

```
git branch -m [<branch-to-rename>] <new-branch name>
git branch --move [<branch-to-rename>] <new-branch-name>
```

- delete a branch

```
git branch -d
git branch --delete
```

- delete a branch regardless of its merge status

```
git branch -D
git branch --delete --force
```

- switch branch

```
git switch <branch-name>
git checkout <branch-name>
```

- create and switch branch

```
git switch -c <branch-name>
git checkout -b <branch-name>
```

- merge with another branch

```
git merge <branch-to-merge-with>
```

## Stashing

- stash changes (put changes into a stash - save changes without committing them)

```
git stash
git stash save
```

- view stash list

```
git stash list
```

- retrieve changes from the stash and remove them

```
git stash pop
```

- retrieve changes from the stash without removing them

```
git stash apply
```

- retrieve changes from a specific stash

```
git stash apply stash@{<#>}

// replace <#> with the stash number
```

- delete a specific stash

```
git stash drop stash@{<#>}

// replace <#> with the stash number
```

- delete all stash

```
git stash clear
```

## Undoing changes and history

- come back to a previous commit - at least the 7 first digit of the commit hash are needed. Do `git switch <branch-name>` to return to last commit of a branch or `git switch -c <new-branch-name>` to move to new branch from previous commit

```
git checkout <commit-hash>

// come back one commit from HEAD (HEAD - 1, HEAD - 2)
git checkout HEAD~1
git checkout HEAD~2
```

- come back to previous branch

```
git switch -
```

- delete changes made since last commit

```
git restore .

// all below does the same
git restore <filename1> <filename2>
git checkout HEAD <filename1> <filename2>
git checkout -- <filename1> <filename2>
```

- unstage files

```
git restore --staged <filename1> <filename2>
```

- soft-reset: delete past commit without deleting changes (useful when working on wrong branch)

```
git reset <commit-hash>
```

- hard-reset: delete past commit AND changes

```
git reset --hard <commit-hash>
```

- make a new commit that removes changes made from past commit

```
git revert <commit-hash>
```

## Working with remote repositories

```
git clone <repo-url>
```

```
git remote -v
git remote add <name> <url>
git remote rename <old-name> <new-name>
git remote remove <name>
```

```
git push
git push <remote> <branch-to-push>
git push -u origin main
git push --set-upstream <remote> <branch-to-push>
```

- get latest changes from remote repository as new branch in local (doesn't merge with current HEAD)

```
git fetch
git fetch <remote>
git fetch <remote> <remote>
```

- retrieve latest changes of from remote repository and merge with current HEAD

```
git pull
git pull <remote> <branch>
```

- view remote branches

```
git branch -r
```

- move to remote branch

```
git switch <remote>
```

- switch to previous commit in a remote branch

```
git checkout <remote>/<branch>
```
