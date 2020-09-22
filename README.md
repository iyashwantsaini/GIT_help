<h1 align="center">
  <br>
  <a href=""><img src="https://raw.githubusercontent.com/meyash/GIT_help/master/git.png" alt="logo" width="400"></a>
  <br>
    GIT - Version Control System
  <br>
</h1>

<h4 align="center">All basic GIT commands and usage!</h4>

## git config

- git config --global user.name "FIRST_NAME LAST_NAME"
- git config --global user.email "MY_NAME@example.com"

## git init

- To initialize a repository with git.

```
> git init
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

## git log

- to get info on previous commits
- last commit is the HEAD in our branch
- press UP/DOWN to see all.
- press "q" to quit.

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
- get "\_commit_id" from "git log"

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

- revert/delete all unstaged changes.

```
> git checkout -- .
```

## git reset

- to delete previous commit(s).
- get the ID of the commit just before the commit you wanna delete.
- all the commits after that commit will be deleted.

```
> git log

commit 840ac517754709a6505ba5358b90c2c186adfe26 (HEAD -> master, origin/master, origin/HEAD)
Author: meyash <yashsn2127@gmail.com>
Date:   Tue Aug 18 20:28:28 2020 +0530

    ten_added

commit 2e316e281b8419e7d3857f261a83fd3782f3f743
Author: meyash <yashsn2127@gmail.com>
Date:   Tue Aug 18 19:43:06 2020 +0530

    nine_added

commit 30fc8d60617f67d23d9e15f4c7ceb7818875978f
Author: meyash <yashsn2127@gmail.com>
Date:   Tue Aug 18 19:36:58 2020 +0530

    eight_added

> git reset --head _commit_id (of the commit just before the commit you wanna delete)
> git reset --head 2e316e281b8419e7d3857f261a83fd3782f3f743 (nine_added)

> git log (now nine_added will be the head)

commit 2e316e281b8419e7d3857f261a83fd3782f3f743 (HEAD -> master, origin/master, origin/HEAD)
Author: meyash <yashsn2127@gmail.com>
Date:   Tue Aug 18 19:43:06 2020 +0530

    nine_added

commit 30fc8d60617f67d23d9e15f4c7ceb7818875978f
Author: meyash <yashsn2127@gmail.com>
Date:   Tue Aug 18 19:36:58 2020 +0530

```

## git branch

- to get name of current working branch

```
> git branch

* master
```

- adding a new branch
- any commits to new branch stays in that branch only.

```
> git checkout -b branch_name

> git branch

* branch_name
  master
```

- merging two branches (after commiting in new branch)

```
> git checkout master

Switched to branch 'master'
Your branch is up to date with 'origin/master'.

> git merge branch_name

Updating f4d8e6d..faa43be
Fast-forward
 README.md                                          | 49 +++++++++++++++++-----
 et --hard 2e316e281b8419e7d3857f261a83fd3782f3f743 | 41 ------------------
 2 files changed, 38 insertions(+), 52 deletions(-)
 delete mode 100644 et --hard 2e316e281b8419e7d3857f261a83fd3782f3f743

> git log

commit faa43be813b477570101afc677d82538b954a0b5 (HEAD -> master, branch_name)
Author: meyash <yashsn2127@gmail.com>
Date:   Tue Aug 18 21:00:33 2020 +0530

    12_added

12_added is now head of both master and branch_name.
```

- deleting the new branch (like after merging)

```
> git branch -D branch_name
```

- Merging when two branches have different changes at same place.
- This is called a conflict.
- You can keep current commit, keep incoming (from the other branch), or keep both.

```
Resolve and commit again in the current branch.
```

## git remote

- to establish a connection between our local and remote repository.

```
> git remote add origin https://github.com/meyash/GIT_help.git

> git remote

origin

> git remote -v

origin  https://github.com/meyash/GIT_help.git (fetch)
origin  https://github.com/meyash/GIT_help.git (push)
```

- to remove remote repo

```
> git remote rm origin
```

## git push

- to upload code from our local to remote repository.
- "U" establishes an upstream for our connectoin.

```
git push -U origin master
```

## git pull

- to get changes made in the remote repo.

```
> git fetch
> git checkout master
> git merge origin/master

OR (all steps in one)

> git pull

```

## git stash

- to save your current code as draft and jump to last commit.
- use stash in this case instead of using commit.

```
> git stash

Saved working directory and index state WIP on master: cc696f3 18_added
```

- to apply last draft to current branch

```
> git stash apply
```

- to view all drafts

```
> git stash list

stash@{0}: WIP on master: cc696f3 18_added
```

- to apply a particular draft to our current branch.

```
> git stash apply 0 (index of the stash we wanna apply)
```

- to save a description with the stash (for easy navigation)

```
> git stash push -m "_description_here"
```

- to delete a stash

```
> git stash drop 2 (index of stash you wanna remove)
```

- to apply stash to current branch and delete it from stash list

```
> git stash pop 2 (index)
```

- delete all stashes

```
> git stash clear
```

## git merge

- Suppose we have 2 branches "one" and "two"
- "one" has commits o1,o2
- "two" has commits t1,t2,t3
- we wanna merge t3 with o2
- such that "one" now has o1,o2,t3(having t2,t1 merged within) commits

```
> git checkout one
> git merge two (but this will merge all commits of "two" in "one")
```

- so we'll use squash here.

## git squash

- to merge all the commits of the current branch in 1 last commit.

```
> git merge --squash _branch_name 
> git commit -m "all_merged" (this commit will have all the previous commits merged)
```

## git rebase

- Suppose we have 2 branches "one" and "two"
- "one" has commits o1,o2,o3,o4
- "two" has commits t1,t2,t3
- we wanna get o4 as the base of two
- such that "two" now has o4,t1,t2,t3 commits

```
> git checkout two
> git rebase master
> git log (to check)
```

## License

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

By [Yashwant](https://github.com/meyash)

## Contributors

<img src="https://avatars3.githubusercontent.com/u/21121279?s=460&u=f0450278b2b569c4443ab8ee03f9dff7015da5bf&v=4" width="100px;" alt="toofff"/><br />

<a href="https://meyash.xyz/" style="margin-right:30px;"><img src="https://meyash.xyz/assets/icons/siteicon.png" width="25"></a>
<a href="https://meyash.xyz/resume.pdf" style="margin-right:30px;"><img src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/libreoffice.svg" width="25"></a> 
<a href="https://www.linkedin.com/in/meyash21/" style="margin-right:30px;"><img src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" width="25"></a>
<a href="https://twitter.com/meyash21" style="margin-right:30px;"><img src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/twitter.svg" width="25"></a>
<a href="https://www.instagram.com/meyash21/" style="margin-right:30px;"><img src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/instagram.svg" width="25"></a>
<a href="https://www.codechef.com/users/meyash21" style="margin-right:30px;"><img src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/codechef.svg" width="25"></a>  