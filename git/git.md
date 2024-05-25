### course teacher : colt steele

the teacher writes notes in trello

GUI : has listed in documentation

- fast-forward merge

merge made by recursive strategy

- git diff
- git diff head
- git diff b1..b2
- Or
- git diff b1 b2

-git stash
-git stash pop
-git stash apply === pop but stash doesn't delete in source
-git stash list
-git stash drop stash@{0}

# travelling

git checkout 9d8c14s55d

cat .git/HEAD // hash

refs/heads/branch-name

git switch master => go back to master // removes detached head
git switch -

git checkout HEAD~1

### checkout vs switch

git checkout HEAD < file > // resets the file to its original
Or
git checkout -- < file > // resets the file to its original

### git restore

git restore file.txt
git restore --source Head~2 file.txt

#### remove file from being included

git restore --staged secret.txt

#### git reset

regular Vs hard reset

git reset < hash >
git reset --hard < hash >

#### git revert

reset removes completely
revert creates new commit
