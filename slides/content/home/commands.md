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
# Commit messages

![](/img/xkcd_git_commit.png)

---
# Model comit

```
Here’s a model Git commit message:

Capitalized, short (50 chars or less) summary

More detailed explanatory text, if necessary.  Wrap it to about 72
characters or so.  In some contexts, the first line is treated as the
subject of an email and the rest of the text as the body.  The blank
line separating the summary from the body is critical (unless you omit
the body entirely); tools like rebase can get confused if you run the
two together.

Write your commit message in the imperative: "Fix bug" and not "Fixed bug"
or "Fixes bug."  This convention matches up with commit messages generated
by commands like git merge and git revert.

Further paragraphs come after blank lines.

- Bullet points are okay, too

- Typically a hyphen or asterisk is used for the bullet, followed by a
  single space, with blank lines in between, but conventions vary here

- Use a hanging indent
```

From [Tim Pope](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html).

---
# Commit Message

Other useful resources for more explanation.

- [Git Source](https://github.com/git/git/blob/master/Documentation/SubmittingPatches#L103-L141)
- [Chris Beams](https://chris.beams.io/posts/git-commit/)
- [Caleb Thompson](https://robots.thoughtbot.com/5-useful-tips-for-a-better-commit-message)
- [Code Like a Girl](https://code.likeagirl.io/useful-tips-for-writing-better-git-commit-messages-808770609503)

[reference](https://code.likeagirl.io/useful-tips-for-writing-better-git-commit-messages-808770609503)


---

# Branch and Merge

[walkthrough](https://git-scm.com/book/en/v1/Git-Branching-Basic-Branching-and-Merging)

- `checkout`
- `merge`

---
# Share and Update

`push` : Share your code

```
$ git push --set-upstream origin add-inital-slides
Counting objects: 285, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (256/256), done.
Writing objects: 100% (285/285), 6.49 MiB | 8.79 MiB/s, done.
Total 285 (delta 50), reused 0 (delta 0)
remote: Resolving deltas: 100% (50/50), done.
remote:
remote: Create a pull request for 'add-inital-slides' on GitHub by visiting:
remote:      https://github.com/royragsdale/git-101/pull/new/add-inital-slides
remote:
To github.com:royragsdale/git-101.git
 * [new branch]      add-inital-slides -> add-inital-slides
Branch add-inital-slides set up to track remote branch add-inital-slides from
origin.
```

---
# Push

```
$ git status
On branch add-inital-slides
Your branch is ahead of 'origin/add-inital-slides' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working tree clean

$ git push
Counting objects: 13, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (12/12), done.
Writing objects: 100% (13/13), 56.12 KiB | 0 bytes/s, done.
Total 13 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
To github.com:royragsdale/git-101.git
   b76e17b..88b80c1  add-inital-slides -> add-inital-slides
```

---
# Share and Update

`pull` : Update your local copy

```
$ git pull
remote: Enumerating objects: 23, done.
remote: Counting objects: 100% (23/23), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 13 (delta 3), reused 13 (delta 3), pack-reused 0
Unpacking objects: 100% (13/13), done.
From github.com:royragsdale/git-101
   b76e17b..88b80c1  add-inital-slides -> origin/add-inital-slides
Updating b76e17b..88b80c1
Fast-forward
 slides/content/home/background.md     |   2 +-
 slides/content/home/practice.md       |  17 ++++++++++++++
 slides/static/img/xkcd_git_commit.png | Bin 0 -> 53731 bytes
 6 files changed, 146 insertions(+), 3 deletions(-)
 create mode 100644 slides/content/home/practice.md
 create mode 100644 slides/static/img/xkcd_git_commit.png
```

---

# Info

`log` : see the history

```
commit 88b80c1d1085677497ab1e74db69c4d5031529d3
Author: Roy Ragsdale <roy@ragsdale.xyz>
Date:   Mon Oct 1 19:03:33 2018 -0400

    Work through commands

commit b76e17b74f7a6a4a0d69456dfd5485b2a2910fe1
Author: Roy Ragsdale <roy@ragsdale.xyz>
Date:   Mon Oct 1 18:21:30 2018 -0400

    Pixelize Linus
```

---
# Info

```
git log --oneline
* 88b80c1 Work through commands
* b76e17b Pixelize Linus
* 6689733 Add so what
* c212f4f Add new machine sections
* 805c3e3 Add most of background
* 6c28b6a Add initial command list to cover
* 48f6f38 Split out sections into individual files
* b9ffda8 Add initial theming and yo setup
* 364e9cb Vendor reveal-hugo theme to build slide deck
* ea513f0 Initial Commit - add Readme
```

---
# Info

`diff`: see what has changed


```
$ git status
On branch add-inital-slides
Your branch is up-to-date with 'origin/add-inital-slides'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   content/home/commands.md

no changes added to commit (use "git add" and/or "git commit -a")

$ git diff content/home/commands.md
diff --git a/slides/content/home/commands.md b/slides/content/home/commands.md
index f32820a..a86c8bf 100644
--- a/slides/content/home/commands.md
+++ b/slides/content/home/commands.md
@@ -173,16 +173,93 @@ origin.

 ---
+# Push
+
+$ git status
+On branch add-inital-slides
+Your branch is ahead of 'origin/add-in
```
---
# Info

See what has changed on your branch

```
git diff master..
```

---

# Help

```
$ git help <verb>
$ man git-<verb>
```

[reference](https://git-scm.com/book/en/v2/Getting-Started-Getting-Help)

---
# From Scratch
- put it all together
- new machine
- keys!

---
# a workflow

1. Make Sure you are up to date
```
git checkout master
git pull
```

2. Create a branch
```
git checkout -b add-workflow
```

3. Add commmits
```
```

---
# New Machine

You only need to do this on a brand new machine

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com

$ git config --global core.editor "gedit -s"
```

[reference](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

---
# SSH Based Auth 

You only need to do this on a brand new machine

1. Generate a public/private key pair

```
$ ssh-keygen
```

2. Upload the public key (`~/.ssh/id_rsa.pub`)
  - GitHub: https://github.com/settings/keys
  - GitLab: https://gitlab.com/profile/keys

3. Use the `ssh` URI to clone

```
git@github.com:royragsdale/git-101.git
```

{{% /section %}}
