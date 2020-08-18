# GIT Commands

## git init

- To initialize a repository with git.

```
>git init
```

## git status

- to get info on untracked files.

```
> git status

On branch master
Your branch is up to date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        index.html
```

## git add

- to add sigle file to tracking logic.

```
> git add _filename
```

- to add all files to tracking logic.
```
> git add .

> git status

On branch master
Your branch is up to date with 'origin/master'.    

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   README.md 
        new file:   index.html
```

## git commit 

- to add currently tracked files to version of the code that we wanna save.
- "-m" : to give our commit a name

```
git commit -m "commit_short_name"
```

## git branch

- to get current working branch
