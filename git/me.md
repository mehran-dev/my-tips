git branch -a all
git branch -r remote
git branch -l local

git fetch --prune // removes deleted branches in local

# Github

master vs origin/master

git remote -v

git checkout origin/master => it gets you to detached head

git add -a -m "foo "

git checkout origin/x => detach HEAD
===> git switch x

## git fetch vs git pull

git pull < remote > // default is origin

git fetch origin master === git fetch master
this Updates origin/master but not master

pull => updates our working directory
git pull = git fetch + git merge

it matters where you pull its where the merge happens

git pull => // git pull origin EXISTING-BRANCH

### github pages

username.github.io/repo-name

work flow

- centralized
- feature branches

### pull requests And Origin rules

### Rebase

it has 2 purpose

A) merge
B) rewrite history

git rebase master

git rebase --abort

---

git rebase -i HEAD~4

pick
reword
edit
fixup
commit
drop

---

# tags

git tag
git tag -l
git tag -l "17"
git tag -l "17*"
git tag "*beta\*"

git checkout v1.0.5

<!-- normal tag  -->

git tag "tagname"

<!--  anotated tag  -->

git tag -a "tag name "

https://dev.to/vinothmohan/git-an-overview-at-high-level-2ckk

# save credential

[git config --global credential.helper store](https://stackoverflow.com/questions/35942754/how-can-i-save-username-and-password-in-git?page=1&tab=scoredesc#tab-top)
