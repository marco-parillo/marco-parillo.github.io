# marco-parillo.github.io

## Commands
```
$ git config --global user.name "Marco Parillo"
$ git config --global user.email "maparillo@gmail.com"
$ git config --list
$ git clone https://github.com/marco-parillo/marco-parillo.github.io.git
$ git clone git@github.com:marco-parillo/svpn-login.git
$ git clone https://aur.archlinux.org/f5vpn.git
$ git clone git@gitlab.com:44WeWantMore/Bookmarks.git
$ cd marco-parillo.github.io
$ git status
$ git add README.md
$ git diff --staged
$ git commit
$ git commit -m"descriptive message"
$ git remote -v
$ git push
$
$ git fetch origin
$ git merge origin/master
```

## Copy github repo to gitlab

```
cd marco-parillo.github.io
git config --global user.name "44WeWantMore"
git config --global user.email "44wewantmore@protonmail.com"
git remote rename origin old-origin
git remote add origin https://gitlab.com/44WeWantMore/Bookmarks.git
git push -u origin --all
git push -u origin --tags
git status
git config
git config --list
```

## Apply a gitignore retroactively

```
git rm -r --cached . 
git add .
git commit -am "Remove ignored files"
```

## Grab upstream PRs
[H/T](https://gist.github.com/piscisaureus/3342247)

```
$ cd .git
$ cp config config.old
$ vi .git/config

$ diff config.old config
8a9,11
> [remote "upstream"]
>       url = https://github.com/dhabyx/plasma-simpleMonitor.git
>       fetch = +refs/pull/*/head:refs/remotes/upstream/pr/*

$ git fetch upstream
remote: Enumerating objects: 106, done.
remote: Counting objects: 100% (106/106), done.
remote: Total 235 (delta 106), reused 106 (delta 106), pack-reused 129
Receiving objects: 100% (235/235), 91.41 KiB | 2.18 MiB/s, done.
Resolving deltas: 100% (126/126), completed with 35 local objects.
From https://github.com/dhabyx/plasma-simpleMonitor
 * [new ref]         refs/pull/13/head -> upstream/pr/13
 * [new ref]         refs/pull/14/head -> upstream/pr/14
 * [new ref]         refs/pull/15/head -> upstream/pr/15
 * [new ref]         refs/pull/16/head -> upstream/pr/16
 * [new ref]         refs/pull/17/head -> upstream/pr/17
 * [new ref]         refs/pull/18/head -> upstream/pr/18
 * [new ref]         refs/pull/22/head -> upstream/pr/22
 * [new ref]         refs/pull/29/head -> upstream/pr/29
 * [new ref]         refs/pull/30/head -> upstream/pr/30
 * [new ref]         refs/pull/31/head -> upstream/pr/31
 * [new ref]         refs/pull/32/head -> upstream/pr/32
 * [new ref]         refs/pull/33/head -> upstream/pr/33
 * [new ref]         refs/pull/34/head -> upstream/pr/34
 * [new ref]         refs/pull/35/head -> upstream/pr/35
 * [new ref]         refs/pull/36/head -> upstream/pr/36
 * [new ref]         refs/pull/37/head -> upstream/pr/37
 * [new ref]         refs/pull/40/head -> upstream/pr/40
 * [new ref]         refs/pull/44/head -> upstream/pr/44

$ git checkout upstream/pr/31
Note: switching to 'upstream/pr/31'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at f56b7a9 Add Mint to distro list.

$ git switch -c PR31
Switched to a new branch 'PR31'

$ git push --set-upstream origin PR31
Username for 'https://github.com': marco-parillo
Password for 'https://marco-parillo@github.com': 
Enumerating objects: 24, done.
Counting objects: 100% (24/24), done.
Delta compression using up to 4 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (13/13), 7.01 KiB | 7.01 MiB/s, done.
Total 13 (delta 6), reused 12 (delta 5), pack-reused 0
remote: Resolving deltas: 100% (6/6), completed with 6 local objects.
remote: 
remote: Create a pull request for 'PR31' on GitHub by visiting:
remote:      https://github.com/marco-parillo/plasma-simpleMonitor/pull/new/PR31
remote: 
To https://github.com/marco-parillo/plasma-simpleMonitor.git
 * [new branch]      PR31 -> PR31
Branch 'PR31' set up to track remote branch 'PR31' from 'origin'.
```
Then in github.com:

 Your recently pushed branches:

 PR31 (1 minute ago)
 
 Compare & Pull Request
