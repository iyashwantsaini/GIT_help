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
> git commit -m "commit_short_name"

[master 1598d06] commit_short_name   
 1 file changed, 4 insertions(+)
```

## git branch

- to get name of current working branch

```
> git branch

* master
```

## git log

- to get info on previous commits
- last commit is the HEAD in our branch

```
> git log

commit 1598d06b5bfaf85f79281e3bc063c0ba5e3e0917 (HEAD -> master)
Author: meyash <mail@gmail.com>
Date:   Tue Aug 18 19:21:13 2020 +0530

    four_added

commit 7facbe1715c6c5acd8e42526864da63b5e24aad2
Author: meyash <mail@gmail.com>
Date:   Tue Aug 18 19:20:26 2020 +0530

    four_added

commit 8ac3233f402d1cd5f0bd58a0546245428ccfd3e8 (origin/master, origin/HEAD)
Author: Yashwant <mail@gmail.com>
Date:   Tue Aug 18 19:06:00 2020 +0530

    Initial commit
```

