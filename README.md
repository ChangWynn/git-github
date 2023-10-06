# Git - Github

- Summary

  - [Basic Git Commands](#basic-git-commands)
  - [Inspection and Comparison](#inspection-and-comparison)
  - [Branching and Merging](#branching-and-merging)
  - [Stashing](#stashing)
  - [Undoing changes and history](#undoing-changes-and-history)
  - [Working with remote repositories](#working-with-remote-repositories)

- Useful links
  - [Git docs](https://git-scm.com/docs)

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
```

## Inspection and Comparison

- view all commits

```
git log
git log --oneline
```

- view unstaged changes since last commit

```
git diff [<filename>]
```

- view staged changes since last commit

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

- go back to a previous commit - at least the 7 first digit of the commit hash are needed.

```
git checkout <commit-hash>

// come back one commit from HEAD (HEAD - 1, HEAD - 2)
git checkout HEAD~1
git checkout HEAD~2
```

- go back to previous branch

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

- soft-reset: delete prior commits without deleting current changes (useful when working on wrong branch)

```
git reset <commit-hash>
```

- hard-reset: delete prior commit AND current changes

```
git reset --hard <commit-hash>
```

- make a new commit that removes changes made from prior commits

```
git revert <commit-hash>
```

- re-write commit history and add them to the tip of `main`

```
git rebase
```

- re-write commits from HEAD - n commit or commit-hash

```
git rebase -i HEAD~<N>
git rebase --interactive HEAD~<N>
```

## Working with remote repositories

```
git clone <repo-url>
```

- git remote

```
git remote -v
```

```
git remote add <name> <url>
```

```
git remote rename <old-name> <new-name>
```

```
git remote remove <name>
```

- git push

```
git push [<remote>] [<branch>]
```

```
git push -u origin main
git push --set-upstream <remote> <branch-to-push>
```

- get latest changes from remote repository as new branch in local (doesn't merge with current HEAD)

```
git fetch [<remote>] [<branch>]
```

- retrieve latest changes of from remote repository and merge with current HEAD

```
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

## Tags

- create lightweight tag

```
git tag <tagname>
```

- create annotated tag (with netadata such as author, time etc...)

```
git tag -a <tagname> (will open text editor)
```

- create a tag on a previous commit

```
git tag <tagname> <commit-hash>
```

- move a tag to a different commit

```
git tag -f <tagname> <commit-hash>
```

- delete a tag

```
git tag -d <tagname>
```

- view tag list

```
git tag
git tag -l
```

- filter tags

```
git tags -l "<RGEX>"

// i.e: git tags -l "*beta*"
```

- move to a specific tag

```
git checkout <tag>
```

- view tag details

```
git show <tag>
```

- compare tags

```
git diff <tag1> <tag2>
```
