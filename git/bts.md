.git -->

- config

additional configurations

git config --local user.name "my-name"
git config --local user.email "my-email"

- refs
  refs/heads/master
  refs/tags

- HEAD
- objects folder
  **the core of git**

git uses SHA-1 hashing

commits + tree + annotated tags + blob

git hash-object < file > --stdin  
git hash-object < file > --stdin -w //writes

---

git cat-file -p < object-hash >

git cat-file -t 79s25d4ed79s25d4ed79s25d4ed

---

# **git reflog**

reflogs are local only

git reflog show HEAD
git reflog

---

[alias]
s=status
l=log

cm = commit -m

git config --global alias.showbranches branch

you can explore online to get best aliases in net . they give you some functionality you don't have !!!
