# Git

[Git docs](https://git-scm.com/docs)

## Basic Commands

```
git init
```

```
git clone <repo-link>
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

- switch branches

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

```
git restore .
git restore <filename1> <filename2>
```
