+++
weight = 40
+++

{{% section %}}

# The Verbs

---

{{< slide background-image="/img/xkcd_git.png"  background-size="50%" >}}

---
# Core Commands
- setup
- snapshot
- branch and merge
- share and update

---

# Setup

`init`

```
$ git init
Initialized empty Git repository in /home/roy/code/git-101/.git/
```

`clone`

```
$ git clone https://github.com/royragsdale/git-101.git
Cloning into 'git-101'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.

$ ls
git-101
```

---

# What is going on?

`git status`

```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   example.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

---

# git status

---

# Snapshot

A two step process, so you can review your changes.

`add`

```
$ git add example.txt

$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   example.txt
```

`commit`

```
$ git commit
[master 5dc5c7c] Changed example to be SIGSAC specific
 1 file changed, 1 insertion(+), 1 deletion(-)

```

---

# Branch and Merge

- `checkout`
- `merge`

---
# Share and Update

- `push`
- `pull`

---

# Info

- `log`
- `diff`

---
# From Scratch
- new machine
- a workflow

---
# New Machine

---
# a workflow

{{% /section %}}
