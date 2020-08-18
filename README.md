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

commit 8ac3233f402d1cd5f0bd58a0546245428ccfd3e8 (origin/master, origin/HEAD)
Author: Yashwant <mail@gmail.com>
Date:   Tue Aug 18 19:06:00 2020 +0530

    Initial commit
```

## git checkout

- to go to a previous version of our code.
- get "_commit_id" from "git log"

```
> git checkout _commit_id

> git checkout 1598d06b5bfaf85f79281e3bc063c0ba5e3e0917
Note: switching to '1598d06b5bfaf85f79281e3bc063c0ba5e3e0917'.

You are in 'detached HEAD' state. You can look around, make experimental 
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.      

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 1598d06 four_added
```

- to get back to lastest version.

```
> git checkout master

Previous HEAD position was 1598d06 four_added
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
```